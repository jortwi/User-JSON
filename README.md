# User-JSON

Dev Mode allows you to change the functionality of the User Mode by changing the array. By default, all AI Foundry functions use the latest prompt, image, and audio file as input. This can be changed by adding additional properties to the object with `role: "function"`, such as `{role: "function", content: "textToText", prompt: "Hi, can you tell me about the wild west?", max_tokens: 500}`.

Create a basic message:
`{ role: 'assistant', content: 'This is a basic message' }`

Create an AI generated message:
`{ role: 'function', content: 'textToText', messages: [steps({start: 0, end: 2, scriptName: 'script0'})] }`

Ask for user input:
`{ role: "user", content: {content: 'input', type: 'text'} }`

Get part of the script:
`steps({start: 0, end: 3, scriptName: 'script0'})`

Get the content of a message, or user input:
`content(1, 'script0')`

Get the result of an AI request:
`result(1, 'script0')`

If statement (add an additional scripts):

```
{
    role: 'condition',
    content: "content(1, 'script0').includes('yes')",
    true: 'script1',
    false: 'script2'

}
```

Combined:

```
[
    {
        role: "assistant",
        content: 'Hi, how are you today'
    },
    {
        role: 'user',
        content: {content: 'input', type: 'text'}
    },
    {
        role: 'function',
        content: 'textToText',
        messages: steps({start: 0, end: 2, scriptName: 'script0'})
    },
    {
        role: 'assistant',
        content: 'Thank you for this conversation!'
    }

]
```
