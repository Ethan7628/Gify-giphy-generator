**Some hints for the Assignment**

GIPHY has an extensive API with many endpoints, their extensive documentation can be found here:

https://developers.giphy.com/docs/api/#quick-start-guide

Do note that there is a chance <api_key> value may need to be reset. This <api_key> is provided by the GIPHY API and their service may at any point reset or revoke it.
It is simple and free to get a new <api_key> and the steps are outlined in the quick start guide link above

Before you start, head over to the <index.js> file and explore the data which you're getting back. Use the above link for reference as well.

<br/>

1. Explore the API endpoints. When you use <axios> to request the following endpoint:

```js

  async function giphyRequest() {
    const response = await axios.get(`http://api.giphy.com/v1/gifs/trending?api_key=MhAodEJIJxQMxW9XqxKjyXfNYdLoOIym`);
    console.log(response);
  }
  giphyRequest();

```

Take some time to note the following:
  - What is the "shape" of the <data> returned by the <axios> request
  - Play around with the object and see what properties you can access
  - What is the value and 'data type' of accessing <response.status>
  - What is the value and 'data type' of accessing <response.data> ?
  - What is the value and 'data type' of accessing <response.data.data> ?
  - What is the value and 'data type' of accessing <response.data.data[0]> ?

Take time to explore the data as well
  - What is the value of <response.data.data.length> ?
  - What is the value and 'data type' of accessing <response.data.data[0].images> ?
  - What is the value and 'data type' of accessing <response.data.data[0].rating> ?

<br/>

2. What if we slightly alter the parameters to our API request:

```js
  // NOTE THE FOLLOWING: //
  // there is a new value <limit> after the <api_key> : limit=10 //
  async function giphyRequest() {
    const response = await axios.get(`http://api.giphy.com/v1/gifs/trending?api_key=MhAodEJIJxQMxW9XqxKjyXfNYdLoOIym&limit=10`);
    console.log(response);
  }
  giphyRequest();

```
Take some time to note some changes:
  - What is the value of <response.data.data.length> now ?

Take some time to look over the linked quick start guide as well

<br/>

3. To be able to display the GIF, we need the URL to that specific GIF. In your <index.html> file you may want to create an <img> tag to play around with the response data and manualy (at least for now) set the GIF url.

For example: if we wanted the URL for the downsized GIF of the first GIF in our results:
  - Access the APIs (as in the Example 2 above)
  - Note the object in the browser console of <response.data.data[0].images.downsized>
  - Note the <height> <size> <width> <url> properties
  - Try setting this GIF url manualy in your <index.html> file within your <img> tag


<br/>

4. Next think about how you would apply all the previous concepts, including:
  - HTML / CSS
  - Javascript - functions, event listeners and working with objects and arrays
  - APIs 
  - DOM manipulation

Using these concepts, we want the GIFs to show up dynamically in the DOM, we want to search for them based on a provided search query in an HTML form

The endpoint for this would be:

http://api.giphy.com/v1/gifs/search?api_key=<api_key>&q=<search_term>

Where the values for:

<api_key> is our GIPHY api key
<search_term> is the category we are searching for (example q=cartoons)

Good Luck!