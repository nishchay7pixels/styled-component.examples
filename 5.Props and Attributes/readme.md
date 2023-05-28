## Props and Attributes

Styled components pass any known html attributes to the DOM. For eg. 

``` <StyledButton type="submit">Submit</StyledButton>```

Here **submit** will be passed to your styled-component and in the DOM it will be rendered as,

```<button type="submit class="...">Submit</button>```

Styled components allows you to specify these attributes once and then use them along with your styled 
components throughout the code preventing duplication.

For example consider the example of a submit button,

> ./components/SButton/SButton.styles.tsx
```
const SubmitButton = styled(StyledButton).attrs({
    type:'submit'
}) `
    box-shadow: 0 9px #999;
    &:active {
        background-color: ${(props) => props.variant === 'outline'? '#FFF' : '#4caf50'};
        box-shadow: 0 5px #666;
        transform: translateY(4px);
    } 

`
export {SubmitButton}
```