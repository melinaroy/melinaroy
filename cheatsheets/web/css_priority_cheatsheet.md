# 🧾 CSS Priority Cheatsheet

## 🔝 1. Importance

- `!important` has the highest priority (use only when necessary)

```css
p {
  color: red !important;
}
```

## 🧮 2. Specificity of Selectors

The more specific the selector, the higher its weight:

| Selector Type                         | Specificity Value |
|--------------------------------------|-------------------|
| Inline styles (`style=""`)           | 1000              |
| ID selectors (`#id`)                 | 100               |
| Class, pseudo-class (`.class`, `:hover`) | 10            |
| Element/tag (`div`, `p`, `h1`, etc.) | 1                 |

➡️ Total specificity is calculated and the highest wins.

Examples:

```css
div p              /* 1 + 1 = 2 */
.article p         /* 10 + 1 = 11 */
#main .article p   /* 100 + 10 + 1 = 111 */
```

## 🕒 3. Order of Appearance

If two rules have the same specificity, the **last one in the CSS file wins**.

## 🧷 4. Style Origin Priority

From strongest to weakest:

1. Inline styles: `<p style="color: blue">`
2. Internal CSS (`<style>` tag)
3. External CSS (linked file)
4. Browser default styles

## 🔁 Summary

```text
!important                ⬆ strongest
inline style             ⬆
ID (#id)
class (.class), pseudo-class
element (p, div)
order of appearance      ⬇ weakest
```
