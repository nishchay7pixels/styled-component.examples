## Basic Example
As the name suggest styled-components,  well be creating a component that will hold the style for below button.

For that we,
1. start by importing styled from styled-components.

``` import styled from 'styled-components'; ```

2. Now we'll use styled function to define a styled Button component as,

```

const StyledButton = styled.button 
    border: 2px solid #4caf50;
    background-color: #4caf50;
    color: white;
    padding: 15px 32px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    cursor: pointer;
    transition: 0.5s all ease-out;
`
```
3. Then inside out react component we will use it as below,

```

return(
    <div className="App">
        <StyledButton>
            Click Me
        </StyledButton>
    </div>
);

```

NOTE - Generally in large projects, styled components have a seperate file for each component. 

Consider the example below, here the styled component component StyledButton have a seperate file as StyledButton.tsx inside app/components directory.

```
import styled from 'styled-components';
const StyledButton = styled.button 
    border: 2px solid #4caf50;
    background-color: #4caf50;
    color: white;
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
and inside app.tsx it is imported and used as,

```
import StyledButton from './components/StyledButton;

const app = () => {
    return(
        <div className="App">
            <StyledButton>
                Click Me
            </StyledButton>
        </div>
    );
}
export default App;
```

this way StyledButton can be used throughout the application easily.