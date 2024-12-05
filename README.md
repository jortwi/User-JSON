# User-JSON

Dev Mode allows you to change the functionality of the User Mode by changing the array. By default, all AI Foundry functions use the latest prompt, image, and audio file as input. This can be changed by adding additional properties to the object with `role: "function"`, such as `{role: "function", content: "textToText", prompt: "Hi, can you tell me about the wild west?", max_tokens: 500}`.

Soon, the array itself can also be used as parts of the prompt. This is not yet available, but could look like `{role: "function", content: "textToText", messages: [...array, {role: "user", content: "React uninterestedly to the previous message."}]}`
