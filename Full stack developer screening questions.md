
# Git skills

Can you create a fork of this `gist` and push it to your `gist`? 

```js
 Yes
```
How would you make sure that your work doesn't conflict with someone else's code when working on the same project in a team?
```js
Answer: by using new file in preference to an existing one.
By not putting changes at end of our code.
Using push and pull changes more often.

```
Write the command for merging someone's code?
```js
answer: git merge <query>

```

Can you install and run the following library on your system? https://github.com/geelen/git-smart/ 
```js
 
Answer: Yes

```

What are some good branching conventions?
```js

Answer: Using unique Id in brach name
  Using slash as operator
  giving branch with aurthor name
  avoiding using numbers only

```

What are some good commit message conventions?
```js
 
Anwer: Separate subject from body with a blank line
Limit the subject line to 50 characters
Capitalize the subject line
Do not end the subject line with a period
Use the imperative mood when in the subject line
Wrap the body at 72 characters
Use the body to explain what and why the change was made.
Remove unnecessary punctuation marks

```

For bonus points create a github repo or a gist where you commit your answers to each question in a separate commit.


# Screening Questions for ReactJS

Will the following component work? If not why not?

```js
import React from "react"

const myComponent = ({name}) => (
  <div>Hi there! {name}</div>
);
```
<b>Answer: it will work by using props to access name and wrapping it with return statement.</b>
  
  
  
Can you rewrite the above component to use `state` instead of `prop`?

```js
// your solution
import React, { useState } from 'react';
const myComponent = (props) => {
return(
  <div>Hi there! {props.name}</div>
  );
};
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      name: "Muqadam",
    };
  }
  changeName = (newName) => {
    this.setState({name: newName});
  }
  render() {
    return (
      <div>
        <p>My name is {this.state.name}</p>
      </div>
    );
  }
}
```

Why is the following react code wrong? What would be the correct way to set the `state`?

```js
//using setState
this.setState({message: "HelloWorld"})
```

What's wrong with the following ReactJS code?

```js
<button onclick={activateLasers}>
```
Answer: the onclick is used with function. activeLasers is looking for variable not calling function(). 

What are inline conditional expressions? Give an example.

```js
// inline conditional render example:
  function Greeting(props) {
  const signUp = props.singUpStatus;
  if (signUp) {
    return <Main Menu />;
  }
  return <singIn />;
}

ReactDOM.render(
  <Greeting signUp={true} />,
  document.getElementById('root')
);
```

When would you use a `key` prop and why is it important?

```js
// example of using the key prop
  Key prop helps React identify which items have changed, are added, or are removed. Most often we use ID from our data as key
  const default= {
  job:'I would like an internship',
  
}
function Contact() {
  const [topic, setTopic] = React.useState('job')
  return (
    <form>
      <label htmlFor="topic">Topic</label>
      <select id="topic" value={topic} onChange={y => setTopic(y.target.value)}>
        <option value="training">job</option>
   
      </select>
      <label htmlFor="subject">Email Heading</label>
      <input
        id="subject"
        key={topic}
        defaultValue={defaultValuesByTopic[topic]}
      />
      <label htmlFor="body">Email body</label>
      <textarea id="body" />
    </form>
  )
}
```

What are `refs`? Why would you use them?
  ```js
Refs are a function provided by React to access the DOM element and the React element that you might have created on your own.
They allow you to use features of the React library like lifecycle methods, state, and context in functional components without having to worry about rewriting it to a class.
  
  ```
  
What are hooks? Give an example of a component that uses hooks?

```js
 Hooks allow function components to have access to state and other React features. Because of this, class components are generally no longer needed.
// component with hooks
  const MultipleStateVars = () => {
  const [age, setAge] = useState(19)
  const [siblingsNum, setSiblingsNum] = 
    useState(10)

  const handleAge = () => setAge(age + 1)
  const handleSiblingsNum = () => 
      setSiblingsNum(siblingsNum + 1)
 

  return (
    <div>
      <p>Today I am {age} Years of Age</p>
      <p>I have {siblingsNum} siblings</p>

      <div>
        <button onClick={handleAge}>
          Get older! 
        </button>
        <button onClick={handleSiblingsNum}>
            More siblings! 
        </button>
      </div>
    </div>
  )
}
```

# NodeJS/Serverside

What is a RESTful API and how would you document it?

Can you write simple server in Node.js that returns Hello World?

```js
// your solution
  var http = require('http');
http.createServer(function (req, res) {
  res.write('HelloWorld'); 
  res.end(); 
}).listen(8000);
```

Name some techniques for avoiding callback hell?
  
```js
  using async/awai or promises to avoid callback
  async function getUser(id) {
    if (id) {
        return await db.user.byId(id);
    } else {
        throw 'Invalid ID!';
    }
}

try {
	let user = await getUser(123);
} catch(err) {
	console.error(err);
}
  ```
  
