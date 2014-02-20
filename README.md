*This repository is a mirror of the [component](http://component.io) module [jgallen23/aug](http://github.com/jgallen23/aug). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/jgallen23-aug`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*
# aug.js
Aug.js is simple augment/extend library.  If you've used jQuery's $.extend, then you will be familiar with it.

## Installation

download [aug.js](https://github.com/jgallen23/aug/raw/master/dist/aug.js) from dist directory. 

or if you are using node

	npm install aug

## Usage

	//Great for overriding defaults
	var a = { a: 1 };
	var b = { a: 2, b: 3 };
	aug(a, b); //a = { a: 2, b: 3};

	//Combining two objects
	var a = { a: 1 };
	var b = { b: 3 };
	var c = aug({}, a, b); 
	//c = { a: 1, b: 3};

	//Extending a function
	var f = function() {};
	aug(f, {
		prop: 42
	});
	//f.prop == 42

	//Extending a prototype
	var Class1 = function() { };
	Class1.prototype.test = function() {
		return 0;
	};

	aug(Class1.prototype, {
		test2: function() {
			return 5;
		}
	});
	var c = new Class();
	c.test(); //returns 0;
	c.test2(); //returns 5


