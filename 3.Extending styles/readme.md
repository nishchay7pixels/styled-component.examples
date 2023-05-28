## Extending styles

Suppose we want to create a fancy button for our landing page. This button will only be used on the LandingPage. For
this fancy button we want most of the styling of our regular button but we also want to add some custom styling to it
like we want its color to be gradient.

```
import styled from 'styled-components';
import StyledButton from './StyledButton';

const FancyButton = styled(StyledButton) `
    background-image: linear-gradient(to right, #f6d365 0%, #fda085 100%);
    border: none;
`

export default FancyButton;
```
Note in above example unline in StyledButton like in 1.Basic where we used styled.Button, here we have passed another 
styled-component.

Now, in App.tsx we can import this FancyButton alongside StyledButton as

```
import StyledButton from './components/StyledButton;
import FancyButton from './component/FancyButton';
const App = () => {
    return(
        <div className="App">
            <StyledButton varient="outline">Click me!</StyledButton>
            <br/>
            <FancyButton>Click me!</FancyButton>
        </div>
    );
}
```

NOTE - To simplify the file structure and ease our ability to import like components we can do the following change to our
file structure.

Create a new directory as ./components/SButtons and inside move the files StyledButton.tsx and FancyButton.tsx . Now move the
code from both the files into Sbutton.styles.tsx

>./components/SButtons/SButton.styles.tsx
```
import styled from 'styled-components';

export const FancyButton = styled(StyledButton) `
    background-image: linear-gradient(to right, #f6d365 0%, #fda085 100%);
`
export const StyledButton = styled.button 
    border: 2px solid #4caf50;
    background-color: ${(props) => props.varient==='outline'? '#FFF' : '#4caf50'}; // we will be using interpolation here
    color: ${(props) => props.varient==='outline'? '#4caf50' : '#FFF'};
    padding: 15px 32px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    cursor: pointer;
    transition: 0.5s all ease-out;
`

```


Now create another file named as SButton.tsx inside './components/SButtons/' and add below code into it,

```
import { Styledbutton, FancyButton } from './SButton.styled'

export default StyledButton;
export {FancyButton}; 

```

Now in App.tsx import both as,


```
import StyledButton, { FancyButton } from './components/SButton/SButton/;
const App = () => {
    return(
        <div className="App">
            <StyledButton varient="outline">Click me!</StyledButton>
            <br/>
            <FancyButton>Click me!</FancyButton>
        </div>
    );
}
```

Another important feature of styled-components is that they provide polymorphic tags. Consider the below
change in App.tsx,

```
import StyledButton, { FancyButton } from './components/SButton/SButton/;
const App = () => {
    return(
        <div className="App">
            <StyledButton varient="outline">Click me!</StyledButton>
            <br/>
            <FancyButton as='a'>Click me!</FancyButton>
        </div>
    );
}
```
What using polymorpic tag 'as=' will do is that when the component will be rendered on the browser, FancyButton will 
use an Anchor (```<a>```) tag instead of a Button (```<button>```) tag.