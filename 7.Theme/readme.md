## Themes

Styled components have theme support by importing theme provider wrapper component. For example consider the code below,

>In app.tsx
```
import {ThemeProvider} from 'styled-component';

const theme = () => {
    dark: {
        primary: '#000',
        text: '#fff'
    },
    light: {
        primary: '#fff',
        text: '#000'
    }
}

const App = () =>{
    return(
        <ThemeProvider theme={theme}>
            <div className="App>
        
            </div>
        </ThemeProvider>
    );
}

export default App;
```

Now all the Styled components will have access to this theme provided. Now lets create a dark themed button,

```
import styled from 'styled-components';
.
.
.
const DarkButton = styled(StyledButton)`
    border: 2px solid ${props => props.theme.dark.primary};
    background-color: ${props=> props.theme.dark.primary};
    color: ${props=> props.theme.dark.text};
`
export {DarkButton};
```