---
layout: post
title:      "Using React 16 Fragments for the First Time"
date:       2018-02-05 01:58:35 -0500
permalink:  using_react_16_fragments_for_the_first_time
---


React 16 ushered in a flurry of new tools for React developers, including portals, error boundaries, the deprecation of the constructor, and fragments, strings, and arrays instead of divs. In this post, I’m going to show you how to use React fragments and arrays and tell you why they are more effective than divs.


In order to get started, you’ll first need to make sure you update to the latest version of React and Babel. This can be done by entering the following commands in your terminal:

```
yarn add react@^16.2.0 react-dom@^16.2.0
yarn upgrade @babel/core @babel/plugin-transform-react-jsx
```

Once you’ve updated your version of React to 16.2 and Babel to 7, you’re then ready to begin.

In the component where you want to use fragments or an array, it’s necessary to require Fragment from React at the top of the file. This is done like the following:

```
import React, { Component, Fragment} from ‘react’;
```

Finally, you just remove the wrapping div and replace it with the <Fragment> </Fragment>.

```
class Answers extends Component {

render () {
     let answersCard = null
question ? 
sortedAnswers = ( question.answers.sort(function(a,b) { return  (a.count < b.count) ? 1 : ((b.count > a.count) ? -1 : 0)}).map(answer => <Answer key={answer.id} answer={answer} questionId={question.id} /> )) 
: sortedAnswers = ( <p>Loading...</p> )
return (
      <Fragment>
         {sortedAnswers}
      </Fragment>
     )
   }
}
```

While the Fragment is the recommended enclosing syntax for now, soon it will be possible to just use empty strings in-place of the array or fragments <> </> but this is not supported on all devices at this time, so the React docs recommend you continue to use Fragments for the time being.

So if you’re like me, the first time you saw this you were asking yourself why do I care if it’s about the same amount of work to add a div as a fragment?

Well, Dan Abramov himself chimed in on this question on this Stack Overflow [post](https://stackoverflow.com/questions/47761894/why-are-fragments-in-react-16-better-than-container-divs). Essentially, 1) fragments are slightly faster than divs and take up less memory; 2) fragments are more effective for some CSS operations such as Flexbox and CSS Grid, where divs have an impact on the layout; and 3), the DOM is less cluttered when using fragments.

I hope this post helped you update your React skills!
