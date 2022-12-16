# Code Refactor - Accessibilty Standards

## Technology Used 

| Technology Used         | Resource URL           | 
| ------------- |:-------------:| 
| <img src="assets/images/html-logo.svg" alt="html" width="20"/> HTML    | [https://developer.mozilla.org/en-US/docs/Web/HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) | 
| <img src="assets/images/css-logo.svg" alt="css" width="20"/> CSS     | [https://developer.mozilla.org/en-US/docs/Web/CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)      |   
| <img src="assets/images/git-logo.svg" alt="git" width="20"/> Git | [https://git-scm.com/](https://git-scm.com/)     |    

## Description 

[Visit the Deployed Site](https://mccoydidericksen.github.io/code-refactor)

This project is an introduction to code refactoring and the importance of creating websites that adhere to accessibilty standards. I was given starter code (HTML and CSS) to analyze, refactor, and deploy the finished product on github pages.

Web accessibility is an increasingly important consideration for businesses. It ensures that people with disabilities can access a website using assistive technologies such as video captions, screen readers, and braille keyboards. Making a website accessible is also good for business for many reasons, one of them being that accessible sites are better positioned in search engines like Google. It also helps companies avoid litigation that can occur when people with disabilities can't access their website.



## Code Refactor Example

The below HTML code does not include any semantic elements and is poorly constructed.


```html
    <div class="content">
        <div class="search-engine-optimization">
            <img src="./assets/images/search-engine-optimization.jpg" class="float-left" />
            <h2>Search Engine Optimization</h2>
            <p>
                Place text here
            </p>
        </div>
        <div id="online-reputation-management" class="online-reputation-management">
            <img src="./assets/images/online-reputation-management.jpg" class="float-right" />
            <h2>Online Reputation Management</h2>
            <p>
                Place text here
            </p>
        </div>
        <div id="social-media-marketing" class="social-media-marketing">
            <img src="./assets/images/social-media-marketing.jpg" class="float-left" />
            <h2>Social Media Marketing</h2>
            <p>
                Place text here
            </p>
        </div>
```

Converting the above non-semantic div with the class of 'content' to a semantic main tag and changing child div tags to semantic article tags ([Semantic Elements](https://www.w3schools.com/html/html5_semantic_elements.asp)).

```html
    <main class="content">
        <article>
            <img src="./assets/images/search-engine-optimization.jpg" class="float-left" alt="search engine optimization image"/>
            <h2>Search Engine Optimization</h2>
            <p>
                Place text here
            </p>
        </article>
        <article>
            <img src="./assets/images/online-reputation-management.jpg" class="float-right" alt="online reputation management image"/>
            <h2>Online Reputation Management</h2>
            <p>
                Place text here
            </p>
        </article>
        <article>
            <img src="./assets/images/social-media-marketing.jpg" class="float-left" alt="social media marketing image"/>
            <h2>Social Media Marketing</h2>
            <p>
                Place text here
            </p>
        </article>
    </main>

```

This change allowed us to delete unnecessary html class elements and their associated css selectors.

```css
.search-engine-optimization {
    margin-bottom: 20px;
    padding: 50px;
    height: 300px;
    font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    background-color: #0072bb;
    color: #ffffff;
}

.online-reputation-management {
    margin-bottom: 20px;
    padding: 50px;
    height: 300px;
    font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    background-color: #0072bb;
    color: #ffffff;
}

.social-media-marketing {
    margin-bottom: 20px;
    padding: 50px;
    height: 300px;
    font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    background-color: #0072bb;
    color: #ffffff;
}

.search-engine-optimization img {
    max-height: 200px;
}

.online-reputation-management img {
    max-height: 200px;
}

.social-media-marketing img {
    max-height: 200px;
}

.search-engine-optimization h2 {
    margin-bottom: 20px;
    font-size: 36px;
}

.online-reputation-management h2 {
    margin-bottom: 20px;
    font-size: 36px;
}

.social-media-marketing h2 {
    margin-bottom: 20px;
    font-size: 36px;
}
```

Now we can avoid code redundancy by utilizing the article and img tags.

```css
.content article {
    margin-bottom: 20px;
    padding: 50px;
    height: 300px;
    font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    background-color: #0072bb;
    color: #ffffff;
}

.content img {
    max-height: 200px;
}

.content h2 {
    margin-bottom: 20px;
    font-size: 36px;
}

```
## Learning Points 

* Writing HTML code with semantic elements can greatly improve code readability and site performance
* Looking for code redunancy is a great starting place for refactoring code
* A clear understanding of how each piece of code interacts with each other is required before any modifications are made
* There is always an opportunity to improve your code even if the overall functionality is the same 