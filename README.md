# Moser Consulting - Intern Book Store

This is an Angular project for an intern or junior developer to help level up their Angular skills. This project is to build a book store that allows users to browse and buy books. In addition there is some book management functionality that will allow admins to perform CRUD actions on the books.

This project is a step up in complexity and will challenge you a little more. This project is a a lot more structured and will help to reinforce best practices as well as giving you more practice with [PrimeNG](https://www.primefaces.org/primeng/setup). The structure is similar to what you would find in a project here at Moser.

Listed below are the different milestones with tasks and what you can expect to have completed after each one.

Please go through the "**First Steps**" initially so that you're ready. These pages contain important information about how to set up your project as well as good information about the project structure.

## First Steps - DO THESE FIRST IN ORDER

- [Helpful Concepts](./docs/1.helpful-reads.md) - Gives you a very basic refresher on JS/React or teaches you some new concepts to look into more.
- [Initial Setup](./docs/2.setup.md) - Makes sure your dev setup is ready.
- [Project Intro](./docs/3.intro.md) - Details about the project.

## Table of Contents

- [First Milestone - Create a header component](#first-milestone---create-a-header-component)
- [Second Milestone - Display a list of books](#second-milestone---display-a-list-of-books)
- [Third Milestone - Add books to a cart](#third-milestone---add-books-to-a-cart)
- [Fourth Milestone - Check out](#final-milestone---check-out)
- [Fifth Milestone - Manage books](#final-milestone---manage-books)

## Referenced Libraries

- [PrimeNG](https://www.primefaces.org/primeng/setup)
- [Angular](https://angular.io/docs)
- [Prime Icons](https://www.primefaces.org/primeng/icons)

## Helpful Guides

- [Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox)
- [CSS Grid](https://css-tricks.com/snippets/css/complete-guide-grid)
- [Angular Router](https://angular.io/guide/router)
- [Angular Modules](https://angular.io/guide/architecture-modules)
- [SASS Basics](https://sass-lang.com/guide)

## Start Coding

### Reminder - How to Start the App

```bash
ng serve -o
```

or

```bash
npm run
```

### First Milestone - Create a Header Component

For the first task, you will create a header component that should be displayed at the root level. The header should contain a menu icon, site title, and a shopping cart icon.

#### First Milestone - Expected Result

1. In the shared module, create a components folder. Create a a header component in the newly added components folder.
1. A header should be displayed at the top of each page.
1. The header should contain a [pi-bars](https://www.primefaces.org/primeng/icons) icon on the left side.
1. The menu icon should open a [sidebar](https://www.primefaces.org/primeng/sidebar) in which we will add our site navigation (done in a latter milestone). The side bar should open from the left side of the page. Visual [reference](./docs/images/sidebar-example.png).
1. The name of our application should appear in the middle of the header. I will let you come up with the name for the book store :).
1. In the right corner there should be a [pi-shopping-cart](https://www.primefaces.org/primeng/icons) icon.
1. All colors used should be from the [color palette](./src/assets/styles/_colors.scss) provided.
1. Refer [here](./docs/images/header-example.png) for a visual reference.

### Second Milestone - Display a list of books

For this task, you will display a list of books on the **products** page.

#### Second Milestone - Expected Result

1. Create a book service that uses the [in-memory-data service](./src/app/core/services/in-memory-data.service.ts) to retreive a list of books. You should call [api.service](./src/app/core/services/api.service.ts) to make these calls.
1. In the products component, display the list of books in three columns. _Hint: [CSS Grid](https://css-tricks.com/snippets/css/complete-guide-grid/) makes this really simple_.
1. The information for each book should be displayed in a [card](https://www.primefaces.org/primeng/card) and display the title, author, page count, and price. Each card should have a [button](https://www.primefaces.org/primeng/button) that that will let the user "Add to cart". Refer [here](./docs/images/card-example.png) for a visual reference. _Hint: PrimeNG provides built in classes that style our buttons for us_.
1. Add a link in the sidebar to the products page.
1. Users should be able to toggle the sidebar open and close.
1. When you are done the page should look very similar to [this](./docs/images/products-example.png).

## Third Milestone - Add books to a cart

For your third task you will add books to a shopping cart when the "Add to cart" buttons are clicked. You will want to maintain the books in the shopping cart even if the page is refreshed.

Since web sites are stateless you will need to use some form of state management. For this exercise you will use the [local storage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage) API to save the list of books.

#### Third Milestone - Expected Result

1. Create a model that represents a shopping cart item. Your shopping cart item should have properties for a book and the count.
1. Create a shopping cart service that will help you add/update books in your cart. This service should use the [local storage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage) API to add and update books.
1. Your shopping cart should keep a list of the different books the user has added to the cart.
1. Your shopping cart should allow the user to add multiple books to the cart. If a book that is already in the cart is added again we should update the count.
1. You should display the number of item in the cart in the header. You should display this number inside of the cart icon. This number should default to 0 until items are added. Adding items should increase the number. Refer [here](./docs/images/cart-count-example.png) for a visual reference.

## Fourth Milestone - Check out

In this task you will create a check out page that displays the different items in the cart along with their price and count.

#### Fourth Milestone - Expected Result

1. Create a new [module](https://angular.io/guide/architecture-modules) called checkout. Create a componets folder to store your new checkout components.
1. [Lazy load](https://angular.io/guide/lazy-loading-ngmodules) the checkout module.
1. Create a checkout component that displays items in the cart along with their count and price.
1. Display the total cost of the items in the cart. Refere [here](./docs/images/checkout-example.png) for a visual example.
1. Add a "checkout" button that will show a [toast](primefaces.org/primeng/toast) notification that tells the user their order is on the way. Clicking the checkout button should clear the cart and return the user to the products page.

## Fifth Milestone - Manage Books

In the fifth task you will create a book managment page that will let an admin view the list of books. The user should be able to create, edit, and delete books.

#### Fifth Milestone - Expected Result

1. Create a new [module](https://angular.io/guide/architecture-modules) called book-managment. Create a componets folder to store your new checkout components.
1. [Lazy load](https://angular.io/guide/lazy-loading-ngmodules) the book-managment module.
1. Display the list of books using a [table](https://www.primefaces.org/primeng/table). Refer [here](./docs/images/book-table-example.png) for a visual example.
1. There should be inline edit and delete [text buttons](https://www.primefaces.org/primeng/button) to perform those actions on the selected book.
1. Clicking the edit button should take the user to another page with a form pre-populated with the book information. Refer [here](./docs/images/update-book-example.png) for a visual example.
1. Clicking the delete button should remove the book from the table. **The deleted book should also no longer be displayed on the products page**.
1. The user should be able to click an "Add Book" button that will take the user to another page. Refer [here](./docs/images/add-book-example.png) for a visual example.
