# Avalonia ACSS Specification document

## TOC

1. Basic styling
   1. Selectors   
   2. Setter syntax

2. Animations and Colors
   1. Animations
      1. Keyframes
      2. Transitions
   2. Colors and Brushes
      1. Basic colors
      2. Gradients

3. Grids
   1. Grid definitions
   2. Grid layout acss functions

4. Media queries
   1. Media queries

5. Avalonia specifics
   
   1. Dynamic Resources

---

# Basic Styling

## Selectors

Like in regular CSS, with ACSS you can select in a few common ways

```css

button{

   //styling

}



#main-container{

    //styling

}

button.large{

    //styling

}
```

Most normal CSS selectors are supported granted they exist in the official [Avalonia Selector spec](https://docs.avaloniaui.net/docs/reference/styles/style-selector-syntax)



There are a few noticable caveats mostly related to the way css and xaml styling differ:

given the following Control:

```xml
<TabItem />
```

The ACSS selector for a Control has to be camelCase when selecting it using just the Controls Name itself.

```css
tabItem{
    //styling
}
```

Of course naming classes and ids (names in avalonia) is completely up to yourself.

## Setter Syntax

All css property setters are directly translated to Avalonia Setters granted the property is typed correctly.

For example:

```css
button{
    background: #FF0000;
}
```

Is directly translated to:

```xml
<Style Selector="button">
    <Setter Property="Background" Value="#FF0000"/>
</Style>
```

Here too there are some casing caveats for multi word properties as css properties by default are kebab-case for both property name and property value:

```xml
<Button HorizontalContentAlignment="Stretch" Background="LightGray"/>
```

becomes:

```css
button{
    horizontal-content-alignment: stretch;
    background: light-gray;
}
```

it is also worth mentioning that nested properties (for example RotateTransform.Angle)

are written as:

```css
button{
    rotate-transform.angle: 0;
}
```

---

# Animations and Colors

## Keyframes

Just like in regular css, ACSS uses the @keyframes rule to handle keyframing animations:

```css
@keyframes [name]{
    //easing
}
```

for example:

```css
@keyframes fadeOut{
    from{
    opacity: 1
    }
    to{
    opacity:0
    }
}
```

then to use them:

```css
button{
    animation: fadeOut 1s sine-ease-out
}
```

this will translate into the following xaml:


```xml
<Style Selector="Button">
    <Setter Property="Opacity" Value="0"/>
     <Animation Duration="0:0:1" Easing="SineEaseOut"> 
                    <KeyFrame Cue="0%">
                        <Setter Property="Opacity" Value="1"/>
                    </KeyFrame>
                    <KeyFrame Cue="100%">
                        <Setter Property="Opacity" Value="0"/>
                    </KeyFrame>
     </Animation>
</Style>
```
