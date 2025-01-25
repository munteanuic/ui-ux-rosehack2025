# ui-ux-rosehack2025
Repo for instructions and submissions RoseHack 2025

## 1. Set Up a New React Project
Create a new React app:

```
npx create-react-app my-react-app
cd my-react-app
```
This will create a new React app in the my-react-app directory.

## 2. Install Storybook
Now, let’s add Storybook to the React project.

Install Storybook using the following command:

```
npx sb init
```
This will:

- Automatically install Storybook and its dependencies.
- Create Storybook configuration files in the .storybook folder.
- Set up default sample stories for your project.

Verify Storybook setup: After the installation finishes, run Storybook:
```
npm run storybook
```

Storybook should now launch at http://localhost:6006, and you will see the default Storybook UI with example stories.

## 3. Create a UI Component (Example: Button Component)
Let’s create a simple Button component and add it to Storybook.

Create the Button component (```src/components/Button.js```):

```
import React from 'react';

const Button = ({ label, onClick, type, disabled }) => {
    return (
        <button
            className={`btn btn-${type}`}
            onClick={onClick}
            disabled={disabled}
        >
            {label}
        </button>
    );
};

export default Button;
```
Explanation:

```label```: The button’s text.

```onClick```: Event handler for the click event.

```type```: Defines the button style (e.g., primary, secondary).

```disabled```: The button’s disabled state.

## 4. Create a Story for the Button Component
Now, let’s create a Story for the Button component.

Create the Button Story (```src/components/Button.stories.js```):

```
import React from 'react';
import Button from './Button';

export default {
    title: 'Components/Button',
    component: Button,
};

const Template = (args) => <Button {...args} />;

export const Primary = Template.bind({});
Primary.args = {
    label: 'Primary Button',
    type: 'primary',
    disabled: false,
};

export const Secondary = Template.bind({});
Secondary.args = {
    label: 'Secondary Button',
    type: 'secondary',
    disabled: false,
};

export const Disabled = Template.bind({});
Disabled.args = {
    label: 'Disabled Button',
    type: 'primary',
    disabled: true,
};
```
Explanation:

We define different stories for the Button component: Primary, Secondary, and Disabled.
args is used to pass dynamic values to the component's props from the Storybook UI.

## 5. Run Storybook
Once you’ve created the Button component and added the stories, run Storybook again:

```
npm run storybook
```
You should now see your Button component displayed in Storybook at http://localhost:6006, with the ability to interactively modify props like label and disabled.

## 6. Pair Programming Exercise
- Create a new Card component that displays a title, description, and an image.
- Add two variations for the Card: one with an image and one without.
- Add dynamic props (e.g., title, description, imageUrl) so users can modify them in Storybook using Controls.
