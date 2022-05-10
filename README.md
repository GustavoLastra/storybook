# Storybook


## What is it?
* Storybook is an open source tool for building UI components and pages in isolation. 

## Why Storybook?
* Documentation directly located where is being used. Documentation without easy access tend to be old and therefore confusing.
* Improves development process: Helps designers, product owners & developers stay in sync.
    * Hexadecimal colors can be found directly.
    * Layout: Margins and padding sizes are also accessible.
    * Component behavior can be simulated (Input Events): Click, Focus, Hover, etc.
* UI Components are easier to implement since they are independently defined from the application!
  * No need to look for the component in the application
  * Props are no hardcoded
  * Functionality can be documented
* Can be used for fast prototyping without having to start the application. 
* Isolated manual testing from the context there are being used. (No login simulation required)

## What do you need to do?
* npx sb init
* npm run storybook

### Stories

* have .story.tsx file extension in order to be added to the Storybook
* have
  * default export
  * ComponentStory(template)
  * Template binds per props alternative

* Example: 


```
// More on default export: https://storybook.js.org/docs/react/writing-stories/introduction#default-export
export default {
  title: 'Example/Button',
  component: Button,
  // More on argTypes: https://storybook.js.org/docs/react/api/argtypes
  argTypes: {
    backgroundColor: { control: 'color' },
  },
} as ComponentMeta<typeof Button>;

// More on component templates: https://storybook.js.org/docs/react/writing-stories/introduction#using-args
const Template: ComponentStory<typeof Button> = (args) => <Button {...args} />;

export const Primary = Template.bind({});
// More on args: https://storybook.js.org/docs/react/writing-stories/args
Primary.args = {
  primary: true,
  label: 'Button',
};

export const Secondary = Template.bind({});
Secondary.args = {
  label: 'Button',
};

export const Large = Template.bind({});
Large.args = {
  size: 'large',
  label: 'Button',
};

export const Small = Template.bind({});
Small.args = {
  size: 'small',
  label: 'Button',
};
```


