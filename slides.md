---
# try also 'default' to start simple
theme: seriph

# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://images.unsplash.com/photo-1556761175-5973dc0f32e7?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2832&q=80

# apply any windi css classes to the current slide
class: 'text-left'

# https://sli.dev/custom/highlighters.html
highlighter: shiki

# show line numbers in code blocks
lineNumbers: false

# persist drawings in exports and build
drawings:
  persist: false

# page transition
transition: slide-left

# use UnoCSS
css: unocss
---

# Introduction to Lightning Web Components

<div class="abs-bl mx-13  my-8  text-sm text-left">
  <div>Peter Dong</div>
  <div class="text-sm opacity-50">May 18th, 2023</div>
</div>

---
transition: fade-out
---

# Peter Dong


Sr. Salesforce Engineer

- Creating content on <a href="https://space.bilibili.com/12506997" ><ri-bilibili-line />TEXTIL</a>
- Blog & Portfolio <a href="https://dyncan.com"><mdi-blogger />dyncan.com</a>
- LinkedIn <a href="https://www.linkedin.com/in/realpd"><carbon-logo-linkedin />realpd</a>
- GitHub <a href="https://github.com/dyncan"><carbon-logo-github />dyncan</a>
- Say hi at <a href="https://twitter.com/xyzvvw"><carbon-logo-twitter/>@xyzvvw</a>

<style>
  h1 {
    background-color: #2B90B6;
    background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
    background-size: 100%;
    -webkit-background-clip: text;
    -moz-background-clip: text;
    -webkit-text-fill-color: transparent;
    -moz-text-fill-color: transparent;
  }
</style>

---
transition: slide-up

class: px-20
---

# 2014 Web Stack


<div grid="~ cols-1 gap-2" m="-t-2" text-3 >

<div v-click="2">

  ```ts
  Frameworks
  ```

  <ul>
    <li>Data Service</li>
    <li>UI Components</li>
    <li>Component model </li>
    <li>Templates </li>
    <li>Rendering optimization </li>
    <li>Modules </li>
    <li>Language extensions</li>
  </ul>

</div>


<div v-click="1">

  ```ts
  Web Standards
  ```

  <ul>
    <li>ECMAScript 2009</li>
    <li>Events</li>
    <li>Standard Elements</li>
    <li>Rendering</li>
  </ul>

</div>

</div>
  
---
class: px-20
---

# 2023 Web Stack

<div grid="~ cols-1 gap-2" m="-t-2" text-3 >

<div v-click="2">

```ts
Frameworks
```

<ul>
  <li>Specialized services</li>
  <li>Data services</li>
  <li>UI component</li>
</ul>

</div>

<div v-click="1">

```ts
Web Standards
```

<ul>
  <li>Web Components </li>
  <li>Templates </li>
  <li>Custom elements </li>
  <li>Shadow DOM </li>
  <li>Decorators </li>
  <li>Modules </li>
  <li>ECMAScript 2023</li>
  <li>Events </li>
  <li>Standard Elements </li>
  <li>Rendering</li>
</ul>

</div>

</div>

---
layout: image-right
image: https://images.unsplash.com/photo-1517180102446-f3ece451e9d8?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1770&q=80
class: py-4
---

# Web Components

```javascript {all|2-4|7|24|all}
class MyCustomComp extends HTMLElement {
  static get observedAttributes() {
    return ['name', 'type'];
  }
  constructor() {
    super();
    const shadow = this.attachShadow({mode: 'open'});
    const div = document.createElement('div');
    shadow.appendChild(div);
  }
  connectedCallback() {
    console.log('Custom element added to page.');
  }
  disconnectedCallback() {
    console.log('Custom element removed from page.');
  }
  adoptedCallback() {
    console.log('Custom element moved to new page.');
  }
  attributeChangedCallback(name, oldValue, newValue) {
    console.log('Custom element attributes changed.');
  }
}
customElements.define('my-custom-comp', MyCustomComp);
```

<arrow v-click="3" x1="400" y1="360" x2="300" y2="510" color="#564" width="3" arrowSize="1" />

---
class: px-20
---

# Lightning Web Components

<div grid="~ cols-1 gap-2" m="-t-2" text-3 >

<div v-click="2">

```ts
Lightning Web Components
```

<ul>
  <li>Security</li>
  <li>Lightning Data Service</li>
  <li>Base Lightning Components</li>
</ul>

</div>

<div v-click="1">

```ts
Web Standards
```

<ul>
  <li>Web Components </li>
  <li>Templates </li>
  <li>Custom elements </li>
  <li>Shadow DOM </li>
  <li>Decorators </li>
  <li>Modules </li>
  <li>ECMAScript 2023</li>
  <li>Events </li>
  <li>Standard Elements </li>
  <li>Rendering</li>
</ul>

</div>

</div>

---

# Lightning Web Components

```html {all|8|}
<template>
    <lightning-card title="HelloBinding" icon-name="custom:custom14">
        <div class="slds-var-m-around_medium">
            <p>Hello, {greeting}!</p>
            <lightning-input
                label="Name"
                value={greeting}
                onchange={handleChange}
            ></lightning-input>
        </div>
    </lightning-card>
</template>
```

```javascript {all|5-7|all}
import { LightningElement } from 'lwc';

export default class HelloBinding extends LightningElement {
    greeting = 'World';
    handleChange(event) {
        this.greeting = event.target.value;
    }
}
```

---

# Eco-System Benefits

<div v-click="1">
  <ul>
    <li>More standards</li>
  </ul>
</div>

<div v-click="2">
  <ul>
    <li>less proprietary Common component model</li>
  </ul>
</div>

<div v-click="3">
  <ul>
    <li>Transferable skills</li>
  </ul>
</div>

<div v-click="4">
  <ul>
    <li>Easier-to-find / easier-to-ramp-up developers</li>
  </ul>
</div>

<div v-click="5">
  <ul>
    <li>Better performance</li>
  </ul>
</div>

---

# AURA vs LWC

<div grid="~ cols-2 gap-6" m="-t-2" text-3 >

  ```
    AURA
  ```

  ```
    LWC
  ```

  <ul>
    <li>Aura Components cannot be used inside LWC</li>
    <li>Lightning Components take longer to build and deliver.</li>
    <li>Aura Components are Salesforce platform dependent</li>
    <li>The data binding between components for property values is two-way</li>
    <li>The ES5 syntax and ES6 Promises are supported by the Aura Components programming architecture.</li>
  </ul>

  <ul>
    <li>LWC can be included in Aura Components</li>
    <li>LWC improves performance and are much faster to deploy</li>
    <li>LWC are natively supported in the browser and much knowledge of Salesforce is not required.</li>
    <li>The data binding between components for property values is one-way</li>
    <li>Lightning Web Components JavaScript support includes: ECMAScript, ES6, ES7, ES8 (excluding Shared Memory and Atomics), ES9 (including only Object Spread Properties (not Object Rest Properties) way</li>
  </ul>

</div>

---
layout: image-right
image: https://images.unsplash.com/photo-1498050108023-c5249f4df085?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2072&q=80
---

<div class="grid mt-46">
  <h1>Demo Time</h1>
  <p>Lightning Web Components</p>

</div>

---
layout: center
class: text-center
---

# Learn More

[Salesforce Documentations](https://developer.salesforce.com/docs/component-library/documentation/en/lwc) · [Trailhead Apps](https://github.com/trailheadapps) · [Salesforce Dev Blogs](https://developer.salesforce.com/blogs)

---
layout: end
---

