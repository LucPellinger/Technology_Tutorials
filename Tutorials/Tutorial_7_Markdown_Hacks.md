#### Repository
- https://github.com/steemit/condenser
- https://github.com/busyorg/busy

#### What Will I Learn?
In general, you will learn some markdown tricks combined with standard HTML tags. In more details what you will learn:
- Hide-show content
- Writing codeblocks inside codeblocks
- Combining and using italic, bold, superscript, subscript, and/or strikethrough
- Quoting long sentence (using nested blockquotes)
- Aligning Image (left, right, center)
- Using animated inline SVG as an alternative of animated GIF
- Embedding website/webapp

#### Requirements
- Understand basic markdown syntax

#### Difficulty
- Advanced

#### Tutorial Contents
Generally, this tutorial is my personal tips and tricks that I use everyday when writing issue and documentation with markdown.
I want to share it here that I hope it's became usefull. Also, this is my first time trying contributing to utopian community.

> feel free to copas some of the tricks in the comment below to test if it works on steemit/busy.org 😊


## Hide-show content
Standard HTML [`<details>`](https://www.w3schools.com/tags/tag_details.asp) can be used to hide-show some content.
Beware that I use [zero-width-space](https://www.fileformat.info/info/unicode/char/200b/browsertest.htm) in the actual text. (copy paste the text will not work, you need to type it manually).

![animated GIF on how hide-show content works](https://user-images.githubusercontent.com/4953069/39996565-167cc43a-57aa-11e8-8ab3-ad6276264e77.gif)

> Use `<details open>` if you want to make it opened/showed by default

### Actual text

````md
<details>
<summary>title of the content (*not* support **markdown** syntax ~~hmm~~)</summary>

content body (support **markdown** syntax ~~hmm~~)

```json
{
  support: "codeblock to"
}
​```

</details>
````

### Result

<details>
<summary>title of the content (*not* support **markdown** ~~syntax~~)</summary>

content body (support **markdown** ~~syntax~~)

```json
{
  support: "codeblock to"
}
```

</details>

<br/>

## Nested codeblocks
This tricks use [zero-width-space](https://www.fileformat.info/info/unicode/char/200b/browsertest.htm) on child codeblocks ( pair of \``` inside pair of \``` ). Usefull when I'm writing this tutorial.

![animated GIF on how to do make nested-codeblocks works](https://user-images.githubusercontent.com/4953069/39996563-161b4908-57aa-11e8-8ca1-bc49a87c6359.gif)

### Actual text

```md
Some text

```md
some **markdown** content that *need* to be `displayed` in ~~plain text~~

```language
some code or syntax
​```

end
​```
```

### Result

Some text

```md
some **markdown** content that *need* to be `displayed` in ~~plain text~~

```language
some code or syntax
​```

end
```

<br/>

## Combining italic, bold, superscript, subscript, and/or strikethrough
Basic markdown typography can also be combined with other markdown typography (italic, etc) and sometimes it can also be combined with HTML tag `<sup>` and `<sub>`.

![animated GIF on how to combine](https://user-images.githubusercontent.com/4953069/39996564-164b8b90-57aa-11e8-8806-f8b14eaa70ff.gif)

### Actual text

```md
italic-bold -> __*“ ssss”*__

superscript -> Starwars<sup>TM</sup>

superscript-italic -> Starwars<sup>*tm*</sup>

subscript -> F<sub>x</sub>

subscript-bold -> Limit<sub>**min**</sub>

italic-bold-strikethrough -> ~~__*“ ssss”*__~~
```

### Result

italic-bold -> __*“ ssss”*__

superscript -> Starwars<sup>TM</sup>

superscript-italic -> Starwars<sup>*tm*</sup>

subscript -> O<sub>2</sub>

subscript-bold -> Limit<sub>**min**</sub>

italic-bold-strikethrough -> ~~__*“ ssss”*__~~

<br/>

## Quote long sentence
We can use nested blockquotes `>>` combined with italic for creating long sentence famous quote.

![animated GIF on how to make long sentence quote](https://user-images.githubusercontent.com/4953069/39996560-15767176-57aa-11e8-84c7-7c356e7128b3.gif)

### Actual text

```md
> **Sir Charles Antony Richard Hoare**
>> *“I call it my billion-dollar mistake.
It was the invention of the null reference in 1965.
At that time, I was designing the first comprehensive type system for references in an object oriented language ([ALGOL W](https://en.wikipedia.org/wiki/ALGOL_W)).
My goal was to ensure that all use of references should be absolutely safe, with checking performed automatically by the compiler.
But I couldn't resist the temptation to put in a null reference, simply because it was so easy to implement. This has led to innumerable errors, vulnerabilities, and system crashes, which have probably caused a billion dollars of pain and damage in the last forty years.”*
```

### Result

> **Sir Charles Antony Richard Hoare**
>> *“I call it my billion-dollar mistake.
It was the invention of the null reference in 1965.
At that time, I was designing the first comprehensive type system for references in an object oriented language ([ALGOL W](https://en.wikipedia.org/wiki/ALGOL_W)).
My goal was to ensure that all use of references should be absolutely safe, with checking performed automatically by the compiler.
But I couldn't resist the temptation to put in a null reference, simply because it was so easy to implement. This has led to innumerable errors, vulnerabilities, and system crashes, which have probably caused a billion dollars of pain and damage in the last forty years.”*

<br/>

## Aligning Image
Because markdown don't support aligning image, instead of
```md
![example seeing impaired TEXT](httpLinktoPicture.jpg)
```

you can use `<img src="httpLinktoPicture.jpg" alt="example seeing impaired TEXT" />`

![animated GIF on how to align image](https://user-images.githubusercontent.com/4953069/39996561-15aaea0a-57aa-11e8-9a20-d0308b6b1999.gif)


### Actual text

```md
This is the code you need to align images to the left:
<img align="left" width="100" height="100" alt="fidget spinner" src="https://loading.io/spinners/fidget-spinner/lg.fidget-spinner.gif">

---
This is the code you need to align images to the center:
<center>
  <img width="300" alt="fidget spinner" src="https://loading.io/spinners/fidget-spinner/lg.fidget-spinner.gif">
</center>

---
This is the code you need to align images to the right:
<img align="right" width="100" height="100" alt="fidget spinner" src="https://loading.io/spinners/fidget-spinner/lg.fidget-spinner.gif">
```

### Result

This is the code you need to align images to the left:
<img align="left" width="100" height="100" alt="fidget spinner" src="https://loading.io/spinners/fidget-spinner/lg.fidget-spinner.gif">

---
This is the code you need to align images to the center:
<center>
  <img width="100" alt="fidget spinner" src="https://loading.io/spinners/fidget-spinner/lg.fidget-spinner.gif">
</center>

---
This is the code you need to align images to the right:
<img align="right" width="100" height="100" alt="fidget spinner" src="https://loading.io/spinners/fidget-spinner/lg.fidget-spinner.gif">

<br/>

## Animated Inline SVG
Instead of animated GIF, you can use animated SVG to draw an ilustration. Beware that this feature not supported in [IE, Microsoft Edge, and Android browsers prior to version 4.4](https://caniuse.com/#feat=svg-smil). Also, some website like [Github](https://github.com/isaacs/github/issues/316#issuecomment-67740023) doesn't allow inline SVG (and even uploading SVG image).

![animated GIF of me writing and showing animated svg](https://user-images.githubusercontent.com/4953069/39996558-15441b86-57aa-11e8-9d7f-206e6743798b.gif)

### Actual text

```svg
This is what it look like when propeller spinning at
<svg width="120" height="120">
  <g transform="translate(0 30)">
    <rect fill="red" width="120" height="60" rx="60" ry="30" >
          <animateTransform attributeName="transform"
                          type="rotate"
                          from="0 60 30"
                          to="360 60 30"
                          dur="0.0059998800024"
                          repeatCount="indefinite"/>
    </rect>
    <rect fill="blue" width="120" height="60" rx="60" ry="30" >
      <animateTransform attributeName="transform"
                        type="rotate"
                        from="90 60 30"
                        to="450 60 30"
                        dur="0.0059998800024"
                        repeatCount="indefinite"/>
    </rect>
  </g>
  <text x="25%" y="10%">10 000 RPM</text>
  <text x="75%" y="90%">11 N</text>
</svg>
for thrust based on [static thrust equation](https://quadcopterproject.wordpress.com/static-thrust-calculation/)
```

### Result

This is what it look like when propeller spinning at
<svg width="120" height="120">
  <g transform="translate(0 30)">
    <rect fill="red" width="120" height="60" rx="60" ry="30" >
          <animateTransform attributeName="transform"
                          type="rotate"
                          from="0 60 30"
                          to="360 60 30"
                          dur="0.0059998800024s"
                          repeatCount="indefinite"/>
    </rect>
    <rect fill="blue" width="120" height="60" rx="60" ry="30" >
      <animateTransform attributeName="transform"
                        type="rotate"
                        from="90 60 30"
                        to="450 60 30"
                        dur="0.0059998800024s"
                        repeatCount="indefinite"/>
    </rect>
  </g>
  <text x="25%" y="10%">10 000 RPM</text>
  <text x="75%" y="90%">11 N</text>
</svg>
for thrust based on [static thrust equation](https://quadcopterproject.wordpress.com/static-thrust-calculation/)

<br/>

## Embed-share website/webapp

Embedding website `<iframe>` or `<script>`. Not many website support this.

![animated GIF of what embed-share should looks like](https://user-images.githubusercontent.com/4953069/39996562-15e16062-57aa-11e8-8d5a-bbb195571d66.gif)

### Actual text

```md
Using `<script>` tag
<script src="https://gist.github.com/DrSensor/2b45a6eb516b6b8084a4866d10699113.js"></script>

---
Using `<iframe>` tag
<iframe src="https://codesandbox.io/embed/6zk98l6w0k" style="width:100%; height:500px; border:0; border-radius: 4px; overflow:hidden;" sandbox="allow-modals allow-forms allow-popups allow-scripts allow-same-origin"></iframe>
```

### Result

Using `<script>` tag
<script src="https://gist.github.com/DrSensor/2b45a6eb516b6b8084a4866d10699113.js"></script>

---
Using `<iframe>` tag
<iframe src="https://codesandbox.io/embed/6zk98l6w0k" style="width:100%; height:500px; border:0; border-radius: 4px; overflow:hidden;" sandbox="allow-modals allow-forms allow-popups allow-scripts allow-same-origin"></iframe>


<br/><br/>
> End of Tutorials

#### Curriculum
This is [one-shot](https://en.wikipedia.org/wiki/One-shot_(comics)) tutorial, no curriculum.

#### Proof of Work Done
https://gist.github.com/DrSensor/b2a674f42933b2ad6db4c6f7934b32a5