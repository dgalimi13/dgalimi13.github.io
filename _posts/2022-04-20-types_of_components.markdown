---
layout: post
title:      "Types of Components"
date:       2022-04-20 16:26:02 +0000
permalink:  types_of_components
---


React/Redux has been an incredibly powerful tool in my journey to develop more advanced projects. One of its most essential features is its use of components.  According to the official React documentation, "Components let you split the UI into independent, reusable pieces, and think about each piece in isolation". This ability to create clear and concise separation of concerns has proven to be extremely useful in writing code that is easier to both read and debug.

Components can be both static and dynamic in nature. a component such as:

export default class QuoteComponent extends Component {

	render() {
		return (
			<div>
					<p>
						"The most dangerous phrase in the language is, ‘We’ve always done it this way.’"
					</p>
				<br />
				Admiral Grace Hopper
			</div>
		);
	}
}

this type of component is responsible for rendering specific data that is hardcoded into the component. 

however components can also render content dynamically based on props that are passed down to it from a parent component such as in the following component.

render() {
		return (
			<div>
					<p>
						{this.props.quoteContent}
					</p>
				<br />
				{this.props.quoteAuthor}
			</div>
		);
	}
}

Here, the data for the quote is being received by the component and called on by the call to props wrapped in curly braces. its actual value is being declared in its parent component when it renders a given child like so:

<QuoteComponent 
quoteContent="The most dangerous phrase in the language is, ‘We’ve always done it this way.’"
quoteAuthor="Admiral Grace Hopper"
/>

This way both the static and dynamic components display the same information, but the dynamic component upon receiving different props from its parent can display different information but in the same structure/style as its previous version. the dynamic component acts as a template whose appearance can continually change based on the information its being passed.

Components can also be organized based on thier role, such as container vs presentational.

Container components are often more complex than presentational components, they often will utilize global state, make use of lifecycle methods and contain render methods. presentational components are often rendered inside containers because they are mostly only responsible for displaying data. container components are often connected to a store to access global state and presentational components will receive that data and be responsible for rendering it in various styles.

Components can become complex and be a difficult tool to utilize properly, but their ability to separate code into chunks is effective for creating organized easy to utilize code.



