## Adding Pseudo classes

When working with styling one common requirement is to add pseudo classes. For example suppose when you hover over an
element or when an element is in focus.

for example in the StyledButton component used in earlier examples, suppose we want to cahgne color of the button when
pointer is hover over it. the cahnge for this in the code for StyledButton will be as,

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
    &:hover {
        background-color: ${(props) => props.varient!=='outline'? '#FFF' : '#4caf50'}; // we will be using interpolation here
        color: ${(props) => props.varient!=='outline'? '#4caf50' : '#FFF'};
    }
`

```

We can also apply other pseudo classes like we did with hover.