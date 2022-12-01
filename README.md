# When to use Redux or React Context
## Introduction
We can use Redux for more large projects because React Context has a couple of potential disadvantages, and they are potential because they might not matter in the app you're building for example if the project scale is not to big (small - medium sized projects).


An Important thing is that using Context or Redux is not an either or decision as you can use both Contexts and Redux in the same application. Redux for application wide-state, Context for selected multi-component states.

---

### Now let's instead focus on the disadvantages you could be facing with React Context:
![1669466422803](https://user-images.githubusercontent.com/61433385/205170739-32f142da-e3e5-4366-badc-aaf029739144.png)

## [1] Complex Setup or Management
**Firstly:** you can have a very complex setup and managing state with React Context can become quite complex. That definitely depends on the kind of application you're building , so for small or medium-sized projects this limitation will likely not be a problem.
But if you're building a large application an enterprise level application using React Context, you can end up with code like this:

![1669466728950](https://user-images.githubusercontent.com/61433385/205171566-560b2f01-2f6e-4088-8009-a4f8bc0a1166.png)

If you have lot of different States that affect multiple components or the entire app, then you will have many Context Providers for managing these states leading to deeply nested JSX code as a result.


**Secondly:** If you avoided having many Context Providers by having one big Context and one Context Provider for a managing the entire state and all the different kinds of state of your application, you will have large Context Provider component that manages a lot of different things, and therefore itself becomes quite difficult to maintain and manage because it's doing a lot of things, like this:

![1669466984132](https://user-images.githubusercontent.com/61433385/205171785-9c2f803f-f4cf-4b64-aded-9c18e5950052.png)

So you might end up with a large Context that manages authentication, theming, user input, if a modal should be displayed or not, and a lot of other things, and that is a downside.



## [2] Performance
**Firstly:** as a proof of concept we have an official quote by a member of the React team, who pointed out that performance issue saying that Context is great for low-frequency updates like changing a theme, or maybe also authentication, but it's not that great if your data changes a lot.

![1669467633319](https://user-images.githubusercontent.com/61433385/205171565-6311556e-f2f7-4d78-aeca-c187ed6e7918.png)

The post is from 2018, but still that is exactly the Context we are using, React Context which was at this time which is why the post is from that date.

**Secondly:** This team member says that Context is not ready as a replacement for flux like state propagation and Redux is a flux like state management library. So he says that React Context is not really a great replacement for Redux in all scenarios, in all cases.

Therefore that's the second disadvantage, performance can be bad if you're managing the wrong kinds of state with React Context.

---
## Conclusion [Use Context for Low Velocity Data & Redux for High Velocity Data]
To sum up, we have the complex setup and management disadvantage because we may end up with deeply nested JSX code and a lot of different Context Providers or with one huge Context Provider which is not maintainable.

On the other hand we have potential performance issues because we should not use React Context for high-frequency state changes. And again, emphasize that for small or medium-sized apps and even certainty a lot of big apps, this might all not matter. But if we come to Redux we won't suffer from these disadvantages.

---

***Inspired by Maximilian Schwarzmüller***
