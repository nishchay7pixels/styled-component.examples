## Animations

In CSS @keyframe is used to add animation to your component. However this CSS can be overriden and is also not
local to the component its used it.

In styled-components we have a keyframe helper that will handle this animation. Consider below example,

```
import styled, { keyframe } from 'styled-components';

const rotate = keyframes `
    from {
        transform: rotate(0deg);
    },
    to {
        transform: rotate(360deg);
    }
`

const AnimatedLogo = styled.img `
    height: 40vmin;
    pointer-event: none;
    animation: ${rotate} infinite 2s linear;
`

export { AnimatedLogo };

```

Then you can use the logo as below in your component,

```
import {AnimatedLogo} from './components/SButton/SButton';
import logo from './logo.svg';
const App = () => {

    return(
        <div className="App">
            <AnimatedLogo src={logo}> </AnimatedLogo>
        </div>
    );
}

export default App;
```