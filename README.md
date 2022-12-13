<h1 align="center">How to Learn</h1>
<h2 align="center">&copy; Dima Klimkin</h2>
<p align="center"> <a href="https://github.com/kobewinona" target="_blank" rel="noreferrer"> <img src="https://cdn.iconscout.com/icon/free/png-256/github-163-761603.png" alt="github" width="40" height="40"/> </a> </p>

<h3 align="center">languages and tools used in this project</h3>
<p align="center"> <a href="https://www.w3schools.com/css/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/css3/css3-original-wordmark.svg" alt="css3" width="40" height="40"/> </a> <a href="https://www.w3.org/html/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original-wordmark.svg" alt="html5" width="40" height="40"/> </a> <a href="https://code.visualstudio.com/" target="_blank" rel="noreferrer"> <img src="https://cdn.icon-icons.com/icons2/2107/PNG/512/file_type_vscode_icon_130084.png" alt="vscode" width="40" height="40"/> </a> <a href="https://git-scm.com/" target="_blank" rel="noreferrer"> <img src="https://git-scm.com/images/logos/downloads/Git-Icon-Black.png" alt="css3" width="40" height="40"/> </a> <a href="https://en.bem.info/" target="_blank" rel="noreferrer"> <img src="https://miro.medium.com/max/1000/1*AGA-0gdD017hFbxeRR7vdQ.png" alt="css3" width="40" height="40"/> </a> </p>

<br>
<br>

- ► [about this project](#about)
- ► [CSS syntax decoration I used in this project](#about)
- ► [styling of this project](#styling)
- ► [difficulties during this project](#difficulties)

<br>

----

<h3 align="center"> <a name="about"> about this project </a> </h3>

----

This project helped me to better understand basics of HTML and CSS languagues and VSCode and git tools. Also I finally singed up at GitHub which I never wanted to do before since I didn't recognize myself as a developer of any sorts (*still kind of hard to say that about myself since I'm still learing*). I've learnt a lot from building this small page. Most importanly I finally tried using git which scared me a lot before, but now I can do very simple commands and I actually understand what I'm doing (*most of the time* ☺).

The webpage itself is about better ways to learn, remembering new information, mistakes in learning process that have a negative impact on how much of new information you actually absorb and can use well afterwards. While building this page I've learnt about Feynman method of learning which is well reviewed [here](https://www.colorado.edu/artssciences-advising/resource-library/life-skills/the-feynman-technique-in-academic-coaching), but to put it shortly here are the main principles:
1. Step 1 – Study.
2. Step 2 - Teach.
3. Step 3 - Fill the Gaps.
4. Step 4 - Simplify.

Also check ten major principles of effective learning by Josh Kaufman.

----

<h3 align="center"> <a name="about"> CSS syntax decoration I used in this project </a> </h3>

----

To make the code more readable for me I decided to devide rules by their function:

```css
.header__title {
  width: 730px;

  font-size: 102px;
  font-weight: 600;
  line-height: 96px;

  position: relative;
  margin: 0 0 0 64px;

  z-index: 2;
}
```

<br>

**1st** block of lines describes an object in generall:

```css
dev {
  width: 0;
  min-height: 0;
  box-sizing: border-box;
  overflow: hidden;
}
```
>etc.

<br>

**2nd** block of lines describes text and its decoration:

```css
dev {
  color: #fff;
  font-size: 14px;
  font-weight: normal;
  text-align: center;
}
```
>etc.

<br>

**3rd** block of lines describes an object's content layout:

```css
dev {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-between;
  column-gap: 0;
}
```
>etc.

<br>

**4th** block of lines describes an object's position and size:

- *rules' order goes from the furthest* ❏ *to the closest* ■ *to content*

- *rules with sides*  *go from top to the left* ↻

```css
dev {
  position: absolute;
  top: 0;
  right: 0;
  margin: 0;
  border: none;
  padding: 0;
}
```
<img src="https://i.postimg.cc/HkN8sKfB/element.png" />

<br>

**5th** block of lines is just ```z-index``` ☺.

<br>

Inside those made-up blocks of lines I also try to maintain a certain order but sometimes I fail and it's not like anyone will ever see this anyway)

----

<h3 align="center"> <a name="styling"> styling of this project </a> </h3>

----

<h4 align="center"> This is here just so I could add those cool bubbles with colors. </h4>

<br>

**font**

```css
font-family: 'Helvetica Neue', Arial, sans-serif;
```

**colors**

<p> <span style="color: #f2f2f2"> ⬤ </span> dark grey (background) #f2f2f2</p>

<p> <span style="color: #1f1f1f"> ⬤ </span> light grey (background) #1f1f1f</p>

<p> <span style="color: #2f80ed"> ⬤ </span> blue (links, figures) #2f80ed</p>

<p> <span style="color: #000000"> ⬤ </span> black (text) #000000</p>



----

<h3 align="center"> <a name="difficulties"> difficulties during this project </a> </h3>

----

**1 problem**

In ```video``` section I decided to add an ```<abbr>``` tag to give **TED** a translation, but FireFox, GoogleChrome and Safari added an underline to the text. The simpliest solution to get rid of that would be to use css styling, but for some reason it does not override normalize styling, which is this:

```css
abbr[title] {
  border-bottom: none; /* 1 */
  text-decoration: underline; /* 2 */
  text-decoration: underline dotted; /* 2 */
}
```

so this does not work:
```css
.abbreviation {
  text-decoration: none;
}
```

**solution 1**

>for some reason a more specific selector overrides normalize styling just fine:
```css
.section-title .abbreviation {
  text-decoration: none;
}
```

**solution 2**

>not the best way to do the job, but it gets rid of that stupid underline:
```html
<abbr style="text-decoration: none;"></abbr>
```

<br>

**2 problem**

Using BEM Nested structure system caused a problem with absolute paths to files in CSS styling files. For some reason if you ```@import``` a CSS stylesheet it messes up the root folder for that file so all urls to images that I used in single CSS stylesheet stopped working of course.

**solution**

>relative path

<br>
<br>

----

<p align="center">thanks to yandex practicum team</p>
<p align="center"> <a href="https://practicum.yandex.ru/" target="_blank" rel="noreferrer"> <img src="https://pic.rutubelist.ru/user/12/6c/126c75567c0299910e36d7275afec321.jpg" alt="css3" width="40" height="40"/> </a> </p>
<p align="center">♥</p>
