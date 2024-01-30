# tiptap-extension-link

<h3 align="center">
    A link extension that supports fully customizable HTML Attributes, not the uniform configure HTMLAttributes option.
</h3>

<br/>

<p align="center">
  <a href="https://www.npmjs.com/package/tiptap-extension-link">
    <img
     alt="NPM URL"
     src="https://img.shields.io/badge/npm-tiptapExtensionLink?logo=npm">
  </a>
  <img
     alt="version"
     src="https://img.shields.io/badge/version-1.0.0-blue">
</p>

<br>

---

## Install

```shell
npm install tiptap-extension-link -S
```

## Usage

Additional HTMLAttributes parameter added to `setLink`

```js
editor
  .chain()
  .focus()
  .setLink({
    href: "",
    HTMLAttributes: {
      class: "text_link",
      "data-id": appID,
      "data-nickname": nickname,
      "data-path": path,
      "data-type": "text",
      "data-servicetype": "",
      target: "",
    },
  });
```

Creates a link mark with the specified HTMLAttributes.

```js
let { state } = editor;
let mark = state.schema.text("This is the link text", [
  state.schema.marks.link.create({
    href: "",
    HTMLAttributes: {
      class: "text_link",
      "data-id": appID,
      "data-nickname": nickname,
      "data-path": path,
      "data-type": "text",
      "data-servicetype": "",
      target: "",
    },
  }),
]);
const tr = state.tr.insert(state.selection.from, mark);
editor.view.dispatch(tr);
```

## Options

`@tiptap/extension-link` configuration option is still supported.

```js
import Link from "tiptap-extension-link";

const editor = new Editor({
  element: document.querySelector(".editor"),
  extensions: [
    StarterKit,
    Link.configure({ openOnClick: false, HTMLAttributes: { rel: "" } }),
  ],
});
```

## Relations

**@tiptap/extension-link:** https://github.com/ueberdosis/tiptap/tree/develop/packages/extension-link

**tiptap-extension-image-link:** https://github.com/KID-1912/tiptap-extension-image-link

**tiptap-appmsg-editor:** https://github.com/KID-1912/tiptap-appmsg-editor
