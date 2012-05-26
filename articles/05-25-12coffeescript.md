{
	"title" : "What I love about CoffeeScript",
	"date" : "5/25/2012"
}

I enjoy writing CoffeeScript because it is clean and quick. Indented
syntax in general makes me happier to write code. Some programmers
cannot stand this dialect of programming languages, but I feel this is
due to their lack of understanding of whitespace characters and the
issues that may arise from this misunderstanding. 

CoffeeScript's syntax is superb, but the outputted JavaScript is even
better. Wrapping everything in an anonymous protects the global variable
space from being polluted with your shitty code, and localizes the
damage. Object oriented programming is strenuous in JavaScript.
Prototyping === too much work. Classes are much easier to build because we
can just use keywords like 'class', '@', 'extends', 'super' etc. In the
end all of this is compiled to prototyped class in JavaScript, but the
important part is we did not have to write it. 

[Static typed languages](http://en.wikipedia.org/wiki/Static_type#Static_typing) 
provide a 'sense' of security because types are checked during compile time 
rather than runtime. My professor, Dr. Robert Noonan (Professor of programming languages),
 at the College of William & Mary once said it is nice to know that an airplane's software will not
hiccup due to a type conversion error or bad type coercion because (to
his knowledge) all plane software is written in ALGOL, Ada or another
strongly typed static language. This phenomenon could explain the
popularity of dynamic languages in other areas where possible code
errors could never result in death, like the web, mobile platforms, etc. 

As you probably know JavaScript is **not a static typed language**. Thus
I would happily freak out if the pilot announced they have upgraded
their auto pilot software to run on the latest version of JavaScript. 
(First of all, that doesn't make much sense. Second [It's MuthaFuckin
JavaScript](http://distilleryimage3.instagram.com/023be5c0a69c11e1a39b1231381b7ba1_7.jpg)
)
Joking aside, there are ways to reduce the chances of type errors and
type coercion in JavaScript.

      var j = 1;
      var p = '1';
      p == j //true
      p != j //false
      
      p === j //false
      p !== j //true

Or the equivalent CoffeeScript

      j = 1
      p = '1'
      p is j // p === j -> false
      p isnt j // p !== j -> true

CoffeeScript will not let us even write the type coercive boolean
operators != and ==. This is another great way CoffeeScript is making
our JavaScript better. Although type coercion can be a bitch to debug,
I would rather it not change my types.

Bottom line, CoffeeScript let's you write better JavaScript faster. You
can learn more at [CoffeeScript.org](http://coffeescript.org/)
