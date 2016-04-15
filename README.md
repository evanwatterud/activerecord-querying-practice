<!-- Create recipes and comments -->
```recipe = Recipe.create(name: "Brussels sprouts pie")
Comment.create(body: "gross", recipe: recipe)
Comment.create(body: "grosser", recipe: recipe)
Comment.create(body: "grossest", recipe: recipe)

recipe = Recipe.create(name: "Brussels sprouts cider")
Comment.create(body: "gross", recipe: recipe)
Comment.create(body: "grosser", recipe: recipe)
Comment.create(body: "grossest", recipe: recipe)

recipe = Recipe.create(name: "Apple pie")
Comment.create(body: "tasty", recipe: recipe)
Comment.create(body: "amazing", recipe: recipe)

recipe = Recipe.create(name: "Apple cider")
Comment.create(body: "Ok", recipe: recipe)
Comment.create(body: "Not bad", recipe: recipe)
Comment.create(body: "Decent", recipe: recipe)

recipe = Recipe.create(name: "Fudge bars")
Comment.create(body: "Best ever", recipe: recipe)```

How would you return all the recipes in your database?
Recipe.all

How would you return all the comments in your database?
Comment.all

How would you return the most recent recipe posted in your database?
Recipe.order(created_at: :desc).first

How would you return all the comments of the most recent recipe in your database?
Recipe.order(created_at: :desc).first.comments

How would you return the most recent comment of all your comments?
Comment.order(created_at: :desc).first

How would you return the recipe associated with the most recent comment in your database?
Comment.order(created_at: :desc).first.recipe

How would you return all recipes that include the string brussels in them?
Recipe.where("name ~* ?", '[bB]russels')
