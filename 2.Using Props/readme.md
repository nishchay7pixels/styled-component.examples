## Using props in Styled-components

Lets consider the example introduced in 1.Basics StyledButton, the button have a definite color. Suppose we want 
to have the flexibility to modify that varient while using the component StyledButton. One varient will have the 
background as Green and color as white, while the other varient will have background as white and color as green. 
In that case the code for the StyledButton will be modified to use props where we can pass the value as props to 
the styled-component like in this case color.

```
const App = () => {
    return(
        <div className = "App">
            <StyledButton varient="outline">Click Me</StyledButton>
            <StyledButton> Click Me</StyledButton>
        </div>
    );
}
```

the above code is an example of how we can pass value in props which will be used to determine the styling of the button.
The code for StyledButton will be modified as,

```
import styled from 'styled-components';
const StyledButton = styled.button 
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
export default StyledButton;
```