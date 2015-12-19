# Modern C++ Design
*Generic Programming and Design Patterns Applied*

By Andrei Alexandrescu

This book is *full* of template code. My understanding of templates was poor when I first looked at this book and I couldn't make it through the first chapter. Now that I have a better understanding of templates, I want to conquer this book!

## Foreword by Scott Meyers
I have learned a tremendous amount from Scott Meyers' books and talks, so I wanted to read the foreword. In the foreword, Meyers talks about the lack of templates in his books *Effective C++* and *More Effective C++*. He describes his early understanding of templates as being "containers of `T`", which is consistent with my view of templates the first time I tried to read the first chapter of this book.

## 1. Policy-Based Class Design
Alexandrescu makes the distinction between programming and design. Mastering design requires a significant amount of experience. This experience is composed of learning what works and what doesn't. Design requires one to make choices and the trade offs of one choice versus another may not be immediately evident to an inexperienced designer.

The combined utility of templates and multiple inheritance is exposed in terms of policies and policy classes. "A policy defines a class interface or a class template interface." The first example of a policy is the `Creator` policy. This policy specifies a template function called `Create()` that takes no arguments, and returns a pointer to a new instance of `T`. The details of this process are left to the policy implementation. For example, the create function could just return `new T` or `std::malloc(sizeof(T))`.

``` cpp
// Policy
template <typename T>
struct OpNewCreator
{
	static T* Create()
	{
		return new T;
	}
};
```

Classes that use policies are referred to as hosts or host classes.

``` cpp
// Host
template <typename CreationPolicy>
class WidgetManager : public CreationPolicy
{
	// ...
};
```

``` cpp
// Usage 
WidgetManager<OpNewCreator<WidgetManager> > widgetManager;
```

It is strange that we have to specific `WidgetManager` twice in the above snippet. Is there a better way to do this?

## 2. Techniques

## 3. Typelists

## 4. Small-Object Allocation

## 5. Generalized Functors

## 6. Implementing Singletons

## 7. Smart Pointers

## 8. Object Factories

## 9. Abstract Factory

## n. to be continued...
