# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md
    Router: create routes to each view state
    Route: define data via models
    ```

1.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
    ember g route campus/boston
    ```

1.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
    'link-to' allows you to go to the parent directory
    ie: {{#link-to 'campus'}}Back to Campus{{/link-to}}

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
    The first is a nested route that allows you to visit the product view via the products page.
    The second route takes you directly to a product.
    ```

1.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```md
    export default Ember.Route.extend({
      model: function(){
        return [
          {
            movie_id: 123,
          },
        ];
      }
    });
    ```

1.  Inside a template, how do we reference data provided by a Route?

    ```md
    tall and skinny runway models. wait no just models. the regular kind.

    <ul>
    {{#each model as |something|}}
      <li>{{something.name}}</li>
    {{/each}}
    </ul>

    ```
