
# Analysis & Optimization of CSS in React pages.

To create script to analyze `Oxygen classes` & `module.scss` properties. And provide relevent data to optimize / reduce the amount of oxygen classes used & add new oxygen classes as code requirement. To build that we are creating different script's for different scenarios such as:
- Build a script to analyze all `Oxygen classes` used in all our repos, and return the count w.r.t oxygen class. To get a through idea of which classes or not used at all in our Repo's and remove them to reduce `Oxygen classes` Size.
- Build a script to analyze all `module.scss` properties & return thier count w.r.t property & name. And dependent on that data move those css properties in `Oxygen classes`.
- Build a script to analyze all `module.scss` properties & check if those properties are present in our oxygen classes if present keep track of those instances & update those properties for `module.scss` to `Oxygen classes`.


## Implementation


## Script to analyze all `Oxygen classes`

All of our repos React Repos are present in carwaleweb leaving oxygen Repo. For now we will just create a script for carwale --> PWA --> react components where we will go through all the js files and find all the oxgen classes used in our js files and update our count w.r.t the oxygen classes. Most of the ways we define oxygen classes are:

- We need to iterate through all  `js` files.
- in those files first we need to check if the specified import (`import getThemeClasses from '@oxygen/theme';`) is used or not.
- If used we need to get all the oxygen classes which are present in (`getThemeClasses(``)`) function for which most of the Regex pattern which are defined in oxygen classes are given in examples.
- Create an object which is of oxygen classes w.r.t their total use count.
- Show all the oxygen classes which are not used or have zero count.

> Note : There are some cases where we directly pass oxygen classes value in oxygen component need to check if done & how to handle it.

Regex Types of Oxygen Classes.
```jsx
getThemeClasses(`
	pt-3;
	pl-3;
`);
```
```jsx
getThemeClasses(`
        border-width-1;
        ${styles.clearButton};
        bg-white;
    `);
```
```jsx
getThemeClasses(`
        ${isMobile ? "ml-10" : ""};
        bg-white;
    `);
```
```jsx
getThemeClasses(`
        ${isMobile ? styles.clearButton: "bg-white"};
        bg-white;
    `);
```


## Script to analyze all `module.scss` for other properties leaving osygen classes.

Will update.
