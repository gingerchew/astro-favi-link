# FaviLink

A way to stylize your links created by [kat](https://github.com/xxwhirlpool) and Astro-ified by [ginger](https://github.com/gingerchew)

```astro
---
import Link from 'astro-favi-link';
---
<Link href="https://github.com/gingerchew/astro-favi-link">A link to this repo with a fun github favicon at the front</Link>
```

Since all Astro components are exported as `default` you can name it whatever you want as long as it starts with a capital letter.

```astro
---
// technically valid but ill advised
import A from 'astro-favi-link';
---
```

## Props

The same attributes as an `a` anchor element and an optional `after` attribute that places the favicon after the text, and `noStyle` for removing the default styles we provide.

## I don't want to add `noStyle` to every link

You can do something like this to have a no style version in your own components.

```astro
---
import Link from 'astro-favi-link';
import { ComponentProps } from 'astro/types';

interface Props extends Omit<'noStyle', ComponentProps<Link>> {}
---
<Link noStyle {...Astro.props}><slot /></Link>
```