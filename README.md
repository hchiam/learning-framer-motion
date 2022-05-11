# Learning Framer Motion [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://github.com/hchiam/learning-framer-motion/blob/main/LICENSE)

Just one of the things I'm learning. https://github.com/hchiam/learning

Made for React, so it relies on JS and hence uses the main thread (so you should use Framer Motion thoughtfully - CSS doesn't run on the main thread), but you can animate things that just aren't possible to animate with CSS, like transition animation between display modes, or even transitioning between completely different HTML elements!

How? ["FLIP"](https://css-tricks.com/animating-layouts-with-the-flip-technique/#aa-what-is-flip): **F**irst, **L**ast, **I**nvert, **P**lay.

Demos: https://www.framer.com/motion

Docs: https://www.framer.com/docs

Intro: https://www.framer.com/docs/introduction

Example: https://codesandbox.io/s/framer-motion-side-menu-mx2rw

## Notes

https://www.framer.com/docs/examples

https://codesandbox.io/s/framer-motion-side-menu-mx2rw

And then try out stuff like these:

```jsx
import { motion } from "framer-motion";

<motion.div animate={{ x: 100 }} />;

<motion.div animate={{ scale: 0.5 }} />;

<motion.div drag="x" dragConstraints={{ left: -100, right: 100 }} />;

const list = { hidden: { opacity: 0 } };
const item = { hidden: { x: -10, opacity: 0 } };

return (
  <motion.ul animate="hidden" variants={list}>
    <motion.li variants={item} />
    <motion.li variants={item} />
    <motion.li variants={item} />
  </motion.ul>
);

const variants = {
  hidden: { opacity: 0 },
  visible: { opacity: 1 },
}

return (
  <motion.div
    initial="hidden"
    animate="visible"
    variants={variants}
  />
)

<motion.div initial={false} animate={{ x: 100 }} />;

const x = useMotionValue(0);
const opacity = useTransform(x, [-100, 0, 100], [0, 1, 0]);

return <motion.div drag="x"
  dragConstraints={{ left: -100, right: 100 }}
  whileHover={{ scale: 1.1 }}
  whileTap={{ scale: 0.9 }}
  style={{ x, opacity }} />;

const { scrollYProgress } = useViewportScroll();

return <motion.path style={{ pathLength: scrollYProgress }} />;
```

## Start from scratch

TODO (couldn't get it to work with CRA nor with a downloaded copy of the codesandbox to play with locally)
