# **[Create a Basic JavaScript Object](https://github.com/LenaKwon/CodeChallenge/blob/main/JavaScript/freeCodeCamp/Object%20Oriented%20Programming/Create%20a%20Basic%20JavaScript%20Object.md#create-a-basic-javascript-object)**

```jsx
let duck = {
		name: "Aflac",
		numLegs: 2
};
```

# **[Use Dot Notation to Access the Properties of an Object](https://github.com/LenaKwon/CodeChallenge/blob/main/JavaScript/freeCodeCamp/Object%20Oriented%20Programming/Use%20Dot%20Notation%20to%20Access%20the%20Properties%20of%20an%20Object.md#use-dot-notation-to-access-the-properties-of-an-object)**

```jsx
let duck = {
		name: "Aflac",
		numLegs: 2
};
console.log([duck.name](http://duck.name/));
```

# **[Create a Method on an Object](https://github.com/LenaKwon/CodeChallenge/blob/main/JavaScript/freeCodeCamp/Object%20Oriented%20Programming/Create%20a%20Method%20on%20an%20Object.md#create-a-method-on-an-object)**

```jsx
let duck = {
		name: "Aflac",
		numLegs: 2,
		sayName: function() {return "The name of this duck is " + [duck.name](http://duck.name/) + ".";}
};
duck.sayName();
```

# **[Make Code More Reusable with the this Keyword](https://github.com/LenaKwon/CodeChallenge/blob/main/JavaScript/freeCodeCamp/Object%20Oriented%20Programming/Make%20Code%20More%20Reusable%20with%20the%20this%20Keyword.md#make-code-more-reusable-with-the-this-keyword)**

If the variable name changes, any code referencing the original name would need to be updated as well. If an object has many references to its properties there is a greater chance for error.

In the current context, this refers to the object that the method is associated with: duck.

오브젝트 안에서의 this 는 오프젝트와 바인딩됨

```jsx
let duck = {
		name: "Aflac",
		numLegs: 2,
		sayName: function() {return "The name of this duck is " + [this.name](http://this.name/) + ".";}
};
```

# **[Define a Constructor Function](https://github.com/LenaKwon/CodeChallenge/blob/main/JavaScript/freeCodeCamp/Object%20Oriented%20Programming/Define%20a%20Constructor%20Function.md#define-a-constructor-function)**  

Constructor is blueprint for the creation of new objects.

**생성자는 기본적으로 함수형식 을 가지고 있지만 일반함수와 구별하기 위해 몇가지 다른 특징을 가진다.** 

-생성자 이름은 `**대문자**`로 시작, 

-property 세팅할때 `this` 사용,  

-생성자 `안`의 `this` 는 새로 생성될 `new object (instance)` 와 바인딩 된다. 

-보통 함수와는 다르게 `**return 값이 없고**`  property 와 method `정의`만 함

```jsx
function Bird() {
		[this.name](http://this.name/) = "Albert";
		this.color = "blue";
		this.numLegs = 2;
}
```

# **[Use a Constructor to Create Objects](https://github.com/LenaKwon/CodeChallenge/blob/main/JavaScript/freeCodeCamp/Object%20Oriented%20Programming/Use%20a%20Constructor%20to%20Create%20Objects.md#use-a-constructor-to-create-objects)**

Notice that the `new` operator is used when `calling` a constructor. This tells JavaScript to create a `new instance of Bird` called `blueBird`.

```jsx
function Bird() {
		[this.name](http://this.name/) = "Albert";
		this.color  = "blue";
		this.numLegs = 2;
}
```

```jsx
let blueBird = new Bird();
```

# **[Extend Constructors to Receive Arguments](https://github.com/LenaKwon/CodeChallenge/blob/main/JavaScript/freeCodeCamp/Object%20Oriented%20Programming/Extend%20Constructors%20to%20Receive%20Arguments.md#extend-constructors-to-receive-arguments)**

생성자를 통해 instance 오브젝트를 만들면 생성자의 property와 method 가 그대로 복사되어 생성된다. 

각기 다른 특징을 가진 `새` 오브젝트를 만들고 싶을 때에 일일히 property 값을 바꾸는 일은 쉽지 않다. 

대신 생성자에 parameter 인자값을 받고, 그 인자값에 의해 새 인스턴스 오브젝트를 생성시키면 다양한 이름과 색깔의 새 오브젝트를 쉽게 만들 수 있다. 

생성자(constructor)는 그야말로 붕어빵 틀이기 때문에 가장 기본이 되고 공통이 되는 뼈대로 구성되는 것이 좋다. 

```jsx
function Bird(name, color) {
		[this.name](http://this.name/) = name;
		this.color = color;
		this.numLegs = 2;
}
```

```jsx
let cardinal = new Bird("Bruce", "red");
console.log(cardinal.name) //Bruce
console.log(cardinal.color) //red
console.log(cardinal.numLegs) //2
```

# **[Verify an Object's Constructor with instanceof](https://github.com/LenaKwon/CodeChallenge/blob/main/JavaScript/freeCodeCamp/Object%20Oriented%20Programming/Verify%20an%20Object's%20Constructor%20with%20instanceof.md#verify-an-objects-constructor-with-instanceof)**

`instanceof` 를 사용하여 constructor 의 instance 인지 확인해 볼 수 있다.

```jsx
let Bird = function(name, color) {
	[this.name](http://this.name/) = name;
	this.color = color;
	this.numLegs = 2;
}
let crow = new Bird("Alexis", "black");
```

```jsx
crow instanceof Bird; //true
```

Bird constructor(생성자) 를 이용해서 만들지 않은 오브젝트는 인스턴스 오브젤트가 아니다.

```jsx
let canary = {
		name: "Mildred",
		color: "Yellow",
		numLegs: 2
};
```

```jsx
canary instanceof Bird; //false
```

# **[Understand Own Properties](https://github.com/LenaKwon/CodeChallenge/blob/main/JavaScript/freeCodeCamp/Object%20Oriented%20Programming/Understand%20Own%20Properties.md#understand-own-properties)**

`hasOwnProperty()` 는 own property 인지 아닌지 true/false 값을 반환한다. 

```jsx
function Bird(name) {
		[this.name](http://this.name/) = name;
		this.numLegs = 2;
}
let duck = new Bird("Donald");
let canary = new Bird("Tweety");
```

```jsx
let ownProps = [];

for (let property in duck) {
		if(duck.hasOwnProperty(property)) {
				ownProps.push(property);
		}
}
```

```jsx
console.log(ownProps); //["name", "numLegs"]
```

# **[Use Prototype Properties to Reduce Duplicate Code](https://github.com/LenaKwon/CodeChallenge/blob/main/JavaScript/freeCodeCamp/Object%20Oriented%20Programming/Use%20Prototype%20Properties%20to%20Reduce%20Duplicate%20Code.md#use-prototype-properties-to-reduce-duplicate-code)**

프로토타입(공통으로 공유할 내용) 오브젝트를 이용해 중복코드 줄이기. 

위 예시에서 numLegs 가  새 인스턴스를 만들 때 마다 반복되기 때문에 

공통되는 것을 빼내어 Bird 생성자의 prototype으로 지정하기.

```jsx
function Bird(name) {
[this.name](http://this.name/) = name;
}

Bird.prototype.numLegs = 2;
```

# **[Iterate Over All Properties](https://github.com/LenaKwon/CodeChallenge/blob/main/JavaScript/freeCodeCamp/Object%20Oriented%20Programming/Iterate%20Over%20All%20Properties.md#iterate-over-all-properties)**

두 종류의 property `own properties` ,`prototype properties`

프로토타입은 own property 가 아니기 때문에 `hasOwnProperty()` 메서드로는 찾을 수 없다.

```jsx
function Bird(name) {
	[this.name](http://this.name/) = name;  //own property
}
Bird.prototype.numLegs = 2; // prototype property
```

```jsx
let duck = new Bird("Donald");

//Here is how you add duck's own properties to the array `ownProps` 
//and prototype properties to the array `prototypeProps`:

let ownProps = [];
let prototypeProps = [];
```

```jsx
for (let property in duck) {
		if(duck.hasOwnProperty(property)) {
					ownProps.push(property);
		} else {
					prototypeProps.push(property);
		}
}
console.log(ownProps);
console.log(prototypeProps);
```

# **[Understand the Constructor Property](https://github.com/LenaKwon/CodeChallenge/blob/main/JavaScript/freeCodeCamp/Object%20Oriented%20Programming/Understand%20the%20Constructor%20Property.md#understand-the-constructor-property)**

Note: Since the `constructor` property can be overwritten (which will be covered in the next two challenges) it’s generally better to use the `instanceof` method to check the type of an object.

```jsx
let duck = new Bird();
let beagle = new Dog();
```

```jsx
console.log(duck.constructor === Bird); //true
console.log(beagle.constructor === Dog); //true
```

```jsx
function joinBirdFraternity(candidate) {
	if (candidate.constructor === Bird) {
			return true;
	} else {
			return false;
	}
}
```

# **[Change the Prototype to a New Object](https://github.com/LenaKwon/CodeChallenge/blob/main/JavaScript/freeCodeCamp/Object%20Oriented%20Programming/Change%20the%20Prototype%20to%20a%20New%20Object.md#change-the-prototype-to-a-new-object)**

프로토타입들을 일일히 등록할 수 있지만

```jsx

Bird.prototype.numLegs = 2;
Bird.prototype.eat = function() {
console.log("nom nom nom");
}
Bird.prototype.describe = function() {
console.log("My name is " + [this.name](http://this.name/));
}
```

프로토타입들을 한번에 할당할 수 있는 방법으로 쉽게 - 새 오브젝트를 만들기

```jsx
Bird.prototype = {
		numLegs: 2,
		eat: function() {
				console.log("nom nom nom");},
		describe: function() {
				console.log("My name is " + [this.name](http://this.name/));}
};
```


# **[Remember to Set the Constructor Property when Changing the Prototype](https://github.com/LenaKwon/CodeChallenge/blob/main/JavaScript/freeCodeCamp/Object%20Oriented%20Programming/Remember%20to%20Set%20the%20Constructor%20Property%20when%20Changing%20the%20Prototype.md#remember-to-set-the-constructor-property-when-changing-the-prototype)**

위의 코드에서 `Bird.prototype` 을 `오브젝트 형식`으로 등록할 때 `Bird 생성자`의 `프로퍼티`를 **다 지워버리기 때문에** 아래 `duck` 이 Bird의 construct 가 같다는 코드에서 `false` 값이 나온다. 이렇게 덮어쓰는 문제를 방지하기 위해 새 오브젝트에 프로퍼티를 할당할때 constructor 가 Bird 라는 것을 명시해야 한다. 귀찮더라도..

```jsx
duck.constructor === Bird;   //false
duck.constructor === Object; //true
duck instanceof Bird;        //true
```

```jsx
Bird.prototype = {
			constructor: Bird,
			numLegs: 2,
			eat: function() {
				console.log("nom nom nom");
			},
			describe: function() {
				console.log("My name is " + [this.name](http://this.name/));
			}
};
```

# **[Understand Where an Object’s Prototype Comes From](https://github.com/LenaKwon/CodeChallenge/blob/main/JavaScript/freeCodeCamp/Object%20Oriented%20Programming/Understand%20Where%20an%20Object%E2%80%99s%20Prototype%20Comes%20From.md#understand-where-an-objects-prototype-comes-from)**

```jsx
Bird.prototype.isPrototypeOf(duck); //true
```

Bird.prototype 이 duck 오브젝트의 프로토타입인지 알고 싶을 때 `isPrototypeOf()` 메서드 쓴다.


# **[Understand the Prototype Chain](https://github.com/LenaKwon/CodeChallenge/blob/main/JavaScript/freeCodeCamp/Object%20Oriented%20Programming/Understand%20the%20Prototype%20Chain.md#understand-the-prototype-chain)**

몇몇의 예외를 두고, 모든 자바스크립트 objects 는 프로토타입을 가지고 있고,  프로토타입 자체는 오브젝트이며, 프로토타입도 자체의 프로토타입을 가질 수 있다.

```jsx
function Bird(name) {
		[this.name](http://this.name/) = name;
}

typeof Bird.prototype; //Object.prototype
```

```jsx
Object.prototype.isPrototypeOf(Bird.prototype);
```

`hasOwnProperty` 는 `Object.prototype`(오브젝트 프로토타입) 안에 정의된 메서드이며, 이 메서드는 Bird.prototype을 통해 액세스할 수 있으며,  duck 이  액세스할 수 있다.  이것이 `prototype chain` 다.

**( Supertype )—    Object  > Bird  > duck   —(Subtype)**

`Object` 는 자바스크립트의 모든 object 들의 supertype 이다. 그래서 어떤 object 도 `hasOwnProperty()` 메서드를 사용할 수 있는 것이다.


# **[Use Inheritance So You Don't Repeat Yourself](https://github.com/LenaKwon/CodeChallenge/blob/main/JavaScript/freeCodeCamp/Object%20Oriented%20Programming/Use%20Inheritance%20So%20You%20Don't%20Repeat%20Yourself.md#use-inheritance-so-you-dont-repeat-yourself)**

반복되는 프로토타입의 메서드들도 상위타입으로 묶어줌으로써 코드반복을 줄일 수 있다.

```jsx
Bird.prototype = {
		constructor: Bird,
		describe: function() {
			console.log("My name is " + [this.name](http://this.name/));
		}
};
Dog.prototype = {
		constructor: Dog,
		describe: function() {
			console.log("My name is " + [this.name](http://this.name/));
		}
};
```

```jsx
function Animal() { };

Animal.prototype = {
			constructor: Animal,
			describe: function() {
				console.log("My name is " + [this.name](http://this.name/));
			}
};
```

# **[Inherit Behaviors from a Supertype](https://github.com/LenaKwon/CodeChallenge/blob/main/JavaScript/freeCodeCamp/Object%20Oriented%20Programming/Inherit%20Behaviors%20from%20a%20Supertype.md#inherit-behaviors-from-a-supertype)**

```jsx
function Animal() { }
		Animal.prototype.eat = function() {
			console.log("nom nom nom");
};
let animal = new Animal();
let animal = Object.create(Animal.prototype); 
// Object.create을 이용해 animal 오브젝트가 Animal.prototype 이란걸 세팅해두면
// animal 이 효과적으로 Animal prototype 의 프로퍼티를 상속받아 사용할 수 있다.

animal.eat(); //true
animal instanceof Animal;
```

# **[Set the Child's Prototype to an Instance of the Parent](https://github.com/LenaKwon/CodeChallenge/blob/main/JavaScript/freeCodeCamp/Object%20Oriented%20Programming/Set%20the%20Child's%20Prototype%20to%20an%20Instance%20of%20the%20Parent.md#set-the-childs-prototype-to-an-instance-of-the-parent)**

```jsx
Bird.prototype = Object.create(Animal.prototype);
// 이번엔 Object.create을 이용해 Bird프로토타입이 Animal.prototype 이란걸 세팅해두면
```

```jsx
let duck = new Bird("Donald");
duck.eat();
//duck 은 Animal의 모든 프로토타입을 상속받게 된다.
```

# **[Reset an Inherited Constructor Property](https://github.com/LenaKwon/CodeChallenge/blob/main/JavaScript/freeCodeCamp/Object%20Oriented%20Programming/Reset%20an%20Inherited%20Constructor%20Property.md#reset-an-inherited-constructor-property)**

```jsx
function Bird() { }
Bird.prototype = Object.create(Animal.prototype);
let duck = new Bird();
duck.constructor //[Function: Animal]
//Bird 프로토타입은 Animal 프로토타입을 모두 상속받았기 때문에
//Bird 를 상속받은 subtype의 duck 의 생성자가 Animal 로 된 것을 볼 수 있다.
//하지만 우리는 Bird 의 새 인스턴스 오브젝트를 만들때 Bird 를 생성자로 해야한다. 
//아래 코드처럼 지정해줄 수 있다. 
```

```jsx
Bird.prototype.constructor = Bird;
duck.constructor //[Function: Bird]
```

# **[Add Methods After Inheritance](https://github.com/LenaKwon/CodeChallenge/blob/main/JavaScript/freeCodeCamp/Object%20Oriented%20Programming/Add%20Methods%20After%20Inheritance.md#add-methods-after-inheritance)**

상속받은 프로토타입에 새로운 메서드를 추가할 수 있다.

```jsx
function Animal() { }
Animal.prototype.eat = function() {
		console.log("nom nom nom");
};
function Bird() { }
Bird.prototype = Object.create(Animal.prototype);
Bird.prototype.constructor = Bird;
//Bird 프로토타입은 Animal 프로토타입을 상속받은 후, 
//Bird 의 constructor가 supertype 인 Animal 로 올라가지 않도록 Bird로 생성자를 지정해주고

//기본형식
ChildObject.prototype = Object.create(ParentObject.prototype);
```

```jsx
Bird.prototype.fly = function() {
		console.log("I'm flying!");
};
//Bird 프로토타입에 추가하고 싶은 새로운 메서드를 추가한다.

//기본형식
ChildObject.prototype.methodName = function() {...};
```

```jsx
let duck = new Bird();
duck.eat(); //nom nom nom
duck.fly(); //I'm flying!
//Bird를 생성자로 해서 duck 인스턴스로 생성할 수 있고,
//Animal 프로토타입과 Bird 프로토타입도 모두 상속받은 모습이다.
```

# **[Override Inherited Methods](https://github.com/LenaKwon/CodeChallenge/blob/main/JavaScript/freeCodeCamp/Object%20Oriented%20Programming/Override%20Inherited%20Methods.md#override-inherited-methods)**

```jsx
function Animal() { }
Animal.prototype.eat = function() {
		return "nom nom nom";
};
function Bird() { }

Bird.prototype = Object.create(Animal.prototype);
```

```jsx
Bird.prototype.eat = function() {
		return "peck peck peck";
};
let duck = new Bird();
duck.eat() // "peck peck peck"

//duck 이 eat() 이 있는지 없으면 다음 supertype인 Bird 가 eat() 이 있는지 있으면 실행하고 중지. 
//그래서 최상위 supertype인 Animal 의 eat() 까지 reaching 되지 못한다.
```

# **[Use a Mixin to Add Common Behavior Between Unrelated Objects](https://github.com/LenaKwon/CodeChallenge/blob/main/JavaScript/freeCodeCamp/Object%20Oriented%20Programming/Use%20a%20Mixin%20to%20Add%20Common%20Behavior%20Between%20Unrelated%20Objects.md#use-a-mixin-to-add-common-behavior-between-unrelated-objects)**

`새` 와 `비행기`처럼 `fly` 메서드가 있지만 딱히 **관련이 없는** 오브젝트들 간의 프로퍼티와 메서드를 공유하는 방법이 `mixin` 이다. 

```jsx
let flyMixin = function(obj) {
		obj.fly = function() {
				console.log("Flying, wooosh!");
		}
};
//The flyMixin takes any object and gives it the fly method.
```

```jsx
let bird = {
		name: "Donald",
		numLegs: 2
};

let plane = {
		model: "777",
		numPassengers: 524
};

flyMixin(bird);
flyMixin(plane);

//Here `bird` and `plane` are passed into `flyMixin`, 
//which then assigns the `fly` function to each object.
```

Now `bird` and `plane` can both fly:

```jsx
bird.fly();  //"Flying, wooosh!"
plane.fly(); //"Flying, wooosh!"
```

# **[Use Closure to Protect Properties Within an Object from Being Modified Externally](https://github.com/LenaKwon/CodeChallenge/blob/main/JavaScript/freeCodeCamp/Object%20Oriented%20Programming/Use%20Closure%20to%20Protect%20Properties%20Within%20an%20Object%20from%20Being%20Modified%20Externally.md#use-closure-to-protect-properties-within-an-object-from-being-modified-externally)**

위의 코드에서 bird 는 전역변수 이름이다. 어디서든 접근하고 변경할 수 있긴 때문이다.

이것은 보안상 문제가 생길수도 있기 때문에 생성자 안에 변수를 만드는 것이 좋다.

```jsx
[bird.name](http://bird.name/) = "Duffy";
```

```jsx
function Bird() {
		let hatchedEgg = 10;
		this.getHatchedEggCount = function() {
			return hatchedEgg;
		};
}
```

```jsx
let ducky = new Bird();
ducky.getHatchedEggCount();

//This way, the variable can only be accessed and changed by methods 
//also within the constructor function.
```

Here `getHatchedEggCount` is a privileged method, because it has access to the private variable `hatchedEgg`. This is possible because `hatchedEgg` is declared in the same context as `getHatchedEggCount`. In JavaScript, a function always has access to the context in which it was created. This is called `closure`.

# **[Understand the Immediately Invoked Function Expression (IIFE)](https://github.com/LenaKwon/CodeChallenge/blob/main/JavaScript/freeCodeCamp/Object%20Oriented%20Programming/Understand%20the%20Immediately%20Invoked%20Function%20Expression%20(IIFE).md#understand-the-immediately-invoked-function-expression-iife)**

```jsx
(function () {
		console.log("Chirp, chirp!");
})();
```

# **[Use an IIFE to Create a Module](https://github.com/LenaKwon/CodeChallenge/blob/main/JavaScript/freeCodeCamp/Object%20Oriented%20Programming/Use%20an%20IIFE%20to%20Create%20a%20Module.md#use-an-iife-to-create-a-module)**

An immediately invoked function expression (IIFE) is often used to group related functionality into a single object or module.
For example, an earlier challenge defined two mixins:

```jsx
function glideMixin(obj) {
  obj.glide = function() {
    console.log("Gliding on the water");
  };
}
function flyMixin(obj) {
  obj.fly = function() {
    console.log("Flying, wooosh!");
  };
}

```

We can group these mixins into a `module` as follows:

```jsx
let motionModule = (function () {
    return {
      glideMixin: function(obj) {
          obj.glide = function() {
          console.log("Gliding on the water");
          };
      },
      flyMixin: function(obj) {
          obj.fly = function() {
          console.log("Flying, wooosh!");
          };
      }
    }
})();

```

Note that you have an immediately invoked function expression (IIFE) that returns an object `motionModule`.
This returned object contains all of the mixin behaviors as properties of the object.
The advantage of the module pattern is that all of the motion behaviors can be packaged into a single object that can then be used by other parts of your code.
Here is an example using it:

```jsx
motionModule.glideMixin(duck);
duck.glide();

```
