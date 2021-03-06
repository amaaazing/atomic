Atomic is already loaded on this page. See it in action by copy/pasting some of the samples below into the Console window in Developer Tools.

## `GET`

```javascript
atomic.ajax({
	url: 'https://jsonplaceholder.typicode.com/posts'
})
	.success(function (data, xhr) {
		// What do when the request is successful
		console.log('SUCCESS!');
		console.log('xhr.textResponse:');
		console.log(data);
		console.log('xhr:');
		console.log(xhr);
	})
	.error(function () {
		// What do when the request fails
		console.log( 'The request failed!' );
	})
	.always(function (data, xhr) {
		// Code that should run regardless of the request status
		console.log('This always runs...');
	});
```

## `POST`

```javascript
atomic.ajax({
	type: 'POST',
	url: 'https://jsonplaceholder.typicode.com/posts',
	data: {
		title: 'foo',
		body: 'bar',
		userId: 1
	}
})
	.success(function (data, xhr) {
		// What do when the request is successful
		console.log('SUCCESS!');
		console.log('xhr.textResponse:');
		console.log(data);
		console.log('xhr:');
		console.log(xhr);
	})
	.error(function () {
		// What do when the request fails
		console.log( 'The request failed!' );
	})
	.always(function (data, xhr) {
		// Code that should run regardless of the request status
		console.log('This always runs...');
	});
```

## JSONP

```javascript
var myCallback = function (data) {
	console.log(data);
};

atomic.ajax({
	type: 'JSONP',
	url: 'https://jsfiddle.net/echo/jsonp/',
	callback: 'myCallback',
	data: {
		text: 'something',
		par1: 'another',
		par2: 'one-more',
		bool: true
	}
});
```