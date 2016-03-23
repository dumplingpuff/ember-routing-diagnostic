# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md
    The main task you do in router is to set routes or url paths to the correct
    route file.  In the route file that is where you define your model or data.

    ```

1.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
    ember g route campus/boston
    ```

1.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
    What template are you linking from is it application or the campus template?
    campus:
    {{#link-to 'boston'}}{{/link-to}}

    application:
    {{#link-to 'campus.boston'}}{{/link-to}}
    ```

1.  Explain **at least** two differences between the following two route
    definitions.

    ```js
    this.route('products', function () {
      this.route('product', { path: '/:product_id' }); // <= 👀here
    });

    this.route('product', { path: '/products/:product_id' }); // <= 👀 here
    ```

    ```md
    The first route is saying that it is a nested route and that product model will be listed under the products model.
    What happens with the first route is that the products model
    will first render and then the product model will render inside
    of it where there is an outlet.

    The latter is not nested but still a dynamic route, product model
    will load independently of products model. 
    ```

1.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```md
    this.store.find('movies', params.movie_id);
    ```

1.  Inside a template, how do we reference data provided by a Route?

    ```md
      We want to hook the model data into the template.
      {{#each model as |movie|}}
      {{/each}}
    ```
