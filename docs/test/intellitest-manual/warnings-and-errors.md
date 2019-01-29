---
title: "Warnings and errors | Microsoft IntelliTest Developer Test Tool"
ms.date: 05/02/2017
ms.prod: visual-studio-dev15
ms.topic: reference
helpviewer_keywords:
  - "IntelliTest, Warnings and errors"
ms.author: gewarren
manager: jillfra
ms.workload:
  - "multiple"
author: gewarren
---
# Warnings and errors

## Warnings and errors by category

* **Boundaries**
  * [MaxBranches exceeded](#maxbranches-exceeded)
  * [MaxConstraintSolverTime exceeded](#maxconstraintsolvertime-exceeded)
  * [MaxConditions exceeded](#maxconditions-exceeded)
  * [MaxCalls exceeded](#maxcalls-exceeded)
  * [MaxStack exceeded](#maxstack-exceeded)
  * [MaxRuns exceeded](#maxruns-exceeded)
  * [MaxRunsWithoutNewTests exceeded](#maxrunswithoutnewtests-exceeded)<p />

* **Constraint Solving**
  * [Cannot Concretize Solution](#cannot-concretize-solution)<p />

* **Domains**
  * [Need Help To Construct Object](#help-construct)
  * [Need Help To Find Types](#help-types)
  * [Usable Type Guessed](#usable-type-guessed)<p />

* **Execution**
  * [Unexpected Failure During Exploration](#unexpected-exploration)
  * [TargetInvocationException](#targetinvocationexception)<p />

* **Instrumentation**
  * [Uninstrumented Method Called](#uninstrumented-method-called)
  * [External Method Called](#external-method-called)
  * [Uninstrumentable Method Called](#uninstrumentable-method-called)
  * [Testability Issue](#testability-issue)
  * [Limitation](#limitation)<p />

* **Interpreter**
  * [Observed Call Mismatch](#observed-call-mismatch)
  * [Value Stored In Static Field](#value-static-field)

<a name="maxbranches-exceeded"></a>
## MaxBranches exceeded

IntelliTest limits the length of any execution path
that it explores during
[input generation](input-generation.md). This feature
prevents IntelliTest from becoming unresponsive when the
program goes into an infinite loop.

Every conditional and unconditional branch of the
executed and monitored code is counted towards this
limit, including branches that do not depend on the
inputs of the
[parameterized unit test](test-generation.md#parameterized-unit-testing).

For example, the following code consumes branches in
the order of 100:

```csharp
for (int i=0; i<100; i++) { }
```

You can edit the **MaxBranches** option of an
attribute derived from **PexSettingsAttributeBase**,
such as [PexClass](attribute-glossary.md#pexclass)
or [PexMethod](attribute-glossary.md#pexmethod). The
following example effectively removes this bound:

```csharp
[PexMethod(MaxBranches=int.MaxValue)]
public void MyTest(...) {
    // ....
}
```

You can also set the **TestExcludePathBoundsExceeded**
option to inform IntelliTest how generally to deal
with these issues.

In the test code, you can use
[PexSymbolicValue](static-helper-classes.md#pexsymbolicvalue)
to ignore constraints generated by the loop
condition:

```csharp
for (int i=0;
    PexSymbolicValue.Ignore(i<100); // IntelliTest will 'forget' about this path condition
    i++)
{ }
```

<a name="maxconstraintsolvertime-exceeded"></a>
## MaxConstraintSolverTime exceeded

IntelliTest uses a
[constraint solver](input-generation.md#constraint-solver)
to compute new test inputs. Constraint solving can be
a very time consuming process, so IntelliTest allows
you to configure bounds - in particular, **MaxConstraintSolverTime**.

For many applications, significantly increasing the
timeout will not result in better coverage. The
reason for this is that most timeouts are caused by
constraint systems that have no solutions. However,
IntelliTest might not be able to determine that it
is inconsistent without trying all possible solutions,
which will result in a timeout.

<a name="maxconditions-exceeded"></a>
## MaxConditions exceeded

IntelliTest limits the length of any execution path
that it explores during
[input generation](input-generation.md). This feature
prevents IntelliTest from becoming unresponsive when
the program enters an infinite loop.

Each conditional branch that depends on the inputs of the
[parameterized unit test](test-generation.md#parameterized-unit-testing)
is counted towards this limit.

For example, each path in the following code consumes
**n+1** conditions:

```csharp
[PexMethod]
void ParameterizedTest(int n) {
    // conditions are "0<n", "1<n", ..., "!(n<n)"
    for (int i=0; i<n; i++)
    { ... }

    // irrelevant for MaxConditions, since conditions do not depend on input
    for (int i=0; i<100; i++)
    { ... }
}
```

You can edit the **MaxConditions** option of an
attribute derived from **PexSettingsAttributeBase**,
such as [PexClass](attribute-glossary.md#pexclass) or
[PexMethod](attribute-glossary.md#pexmethod). For
example:

```csharp
[PexMethod(MaxConditions=10000)]
void ParameterizedTest(int n) {
    // ...
}
```

You can also set the **TestExcludePathBoundsExceeded**
option to inform IntelliTest how to generally deal
with these issues.

You can use
[PexSymbolicValue](static-helper-classes.md#pexsymbolicvalue)
to ignore constraints generated by the loop
condition:

```csharp
[PexMethod]
void ParameterizedTest(int n) {
    int nshadow = PexSymbolicValue.Ignore(n); // IntelliTest looses track of 'n'

    // irrevelant for MaxConditions, since nshadow is not related to input
    for (int i=0; i<nshadow; i++)
    {...}
}
```

<a name="maxcalls-exceeded"></a>
## MaxCalls exceeded

IntelliTest limits the length of any execution path
that it explores during
[input generation](input-generation.md). This feature
prevents IntelliTest from becoming unresponsive when
the program goes enters an infinite loop.

Each call (direct, indirect, virtual, or jump) of the
executed and monitored code is counted towards this limit.

You can edit the **MaxCalls** option of an attribute
derived from **PexSettingsAttributeBase**, such as
[PexClass](attribute-glossary.md#pexclass) or
[PexMethod](attribute-glossary.md#pexmethod). The
following example effectively removes this bound:

```csharp
[PexMethod(MaxCalls=int.MaxValue)]
public void MyTest(...) {
    // ....
}
```

You can also set the **TestExcludePathBoundsExceeded**
option to inform IntelliTest how to generally
deal with these issues.

<a name="maxstack-exceeded"></a>
## MaxStack exceeded

IntelliTest limits the size of the call stack of any
execution path that it explores during
[input generation](input-generation.md). This feature
prevents IntelliTest from terminating when a stack
overflow occurs.

You can edit the **MaxStack** option of an attribute
derived from **PexSettingsAttributeBase**, such as
[PexClass](attribute-glossary.md#pexclass) or
[PexMethod](attribute-glossary.md#pexmethod). The
following example effectively removes this bound (not recommended):

```csharp
[PexMethod(MaxStack=int.MaxValue)]
public void MyTest(...) {
    // ....
}
```

You can also set the **TestExcludePathBoundsExceeded**
option to inform IntelliTest how to generally
deal with these issues.

<a name="maxruns-exceeded"></a>
## MaxRuns exceeded

IntelliTest limits the number of execution paths that
it explores during
[input generation](input-generation.md). This feature
ensures that IntelliTest terminates when the program
has loops or recursion.

It may not be the case that, every time IntelliTest
runs the parameterized test with particular inputs,
it emits a new test case. See
[TestEmissionFilter](exploration-bounds.md#testemissionfilter)
for more information.

You can edit the **MaxRuns** option of an attribute
derived from **PexSettingsAttributeBase**,such as
[PexClass](attribute-glossary.md#pexclass) or
[PexMethod](attribute-glossary.md#pexmethod). The
following example effectively removes this bound (not recommended):

```csharp
[PexMethod(MaxRuns=2000)]
public void MyTest(...) {
    // ....
}
```

<a name="maxrunswithoutnewtests-exceeded"></a>
## MaxRunsWithoutNewTests exceeded

IntelliTest limits the number of execution paths that
it explores during
[input generation](input-generation.md). This feature
ensures that IntelliTest terminates when the program
has loops or recursion.

It may not be the case that, every time IntelliTest
runs the parameterized test with particular inputs,
it emits a new test case. See
[TestEmissionFilter](exploration-bounds.md#testemissionfilter)
for more information.

While IntelliTest often finds many interesting test
inputs initially, it might not - after a while -
emit any more tests. This option governs how long
IntelliTest may keep trying to find another relevant
test input.

You can edit the **MaxRunsWithoutNewTests** option of
an attribute derived from **PexSettingsAttributeBase**,
such as [PexClass](attribute-glossary.md#pexclass) or
[PexMethod](attribute-glossary.md#pexmethod). The
following example effectively removes this bound (not recommended):

```csharp
[PexMethod(MaxRunsWithoutNewTests=2000)]
public void MyTest(...) {
    // ....
}
```

<a name="cannot-concretize-solution"></a>
## Cannot concretize solution

This error is often the consequence of an earlier
error. IntelliTest uses a
[constraint solver](input-generation.md#constraint-solver)
to determine new test inputs. Sometimes, test inputs
proposed by the [constraint solver](input-generation.md#constraint-solver)
are invalid. This can happen when:

* certain constraints are not known
* if values are created in a user-defined way, causing errors to occur in user code
* some of the types involved have initialization logic not controlled by IntelliTest (for example, COM classes)

<a name="help-construct"></a>
## Need help to construct object

IntelliTest [generates test inputs](input-generation.md),
and some of the inputs may be objects with fields.
Here, IntelliTest tries to generate an instance of a
class that has a private field, and it assumes that
an interesting program behavior will occur when this
private field has a particular value.

However, while
this is possible with Reflection, IntelliTest does
not manufacture objects with arbitrary field values.
Instead, in these cases, it relies on the user to
provide hints about how to use the public methods of
a class to create an object, and bring it into a
state where its private field has the desired value.

Read [Instantiating existing classes](input-generation.md#existing-classes) to learn how you can help IntelliTest construct interesting objects.

<a name="help-types"></a>
## Need help to find types

IntelliTest [generates test inputs](input-generation.md)
for any .NET type. Here, IntelliTest tries to create
an instance that derives from an abstract class or
implements an abstract interface, and IntelliTest
does not know of any type that fulfills the
constraints.

You can help IntelliTest by pointing to one or more
types that match the constraints. Usually, one of
the following attributes will help:

* **PexUseTypeAttribute**, which points to a particular type.

  For example, if IntelliTest reports that it "does not know of any types assignable to **System.Collections.IDictionary**", you can help it by attaching the following **PexUseTypeAttribute** to the test (or to the fixture class):

  ```csharp
  [PexMethod]
  [PexUseType(typeof(System.Collections.Hashtable))]
  public void MyTest(IDictionary[] dictionaries) { ... }
  ```

* **An assembly-level attribute**

  ```csharp
  [assembly: PexUseType(typeof(System.Collections.Hashtable))]
  ```

<a name="usable-type-guessed"></a>
## Usable type guessed

IntelliTest [generates test inputs](input-generation.md)
for any .NET types. When a type is abstract or an
interface, IntelliTest must choose a particular
implementation of that type. To make that choice, it
needs to know which types exist.

When this warning is shown, it indiicates that IntelliTest looked at some
of referenced assemblies and found an implementation
type, but it is not sure if it should use that type,
or if there are more appropriate types available
elsewhere. IntelliTest simply chose a type that
looked promising.

In order to avoid this warning, you can either
accept IntelliTest's type choice, or assist IntelliTest
in using other types by adding a corresponding
[PexUseType](attribute-glossary.md#pexusetype).

<a name="unexpected-exploration"></a>
## Unexpected failure during exploration

An unexpected exception was caught while exploring a test.

Please [report this as a bug](#report-bug).

<a name="targetinvocationexception"></a>
## TargetInvocationException

An exception occurred in user code. Inspect the stack trace, and remove the bug in your code.

<a name="uninstrumented-method-called"></a>
## Uninstrumented method called

IntelliTest [generates test inputs](input-generation.md)
by monitoring program execution. It is essential that
the relevant code is properly instrumented so that
IntelliTest can monitor its behavior.

This warning appears when the instrumented code
calls methods in another, uninstrumented assembly.
If you want IntelliTest to explore the interaction of
both, you must also instrument the other assembly
(or parts of it).

<a name="external-method-called"></a>
## External method called

IntelliTest [generates test inputs](input-generation.md)
by monitoring execution of .NET applications.
IntelliTest cannot generate meaningful test inputs
for code that is not written in a .NET language.

This warning appears when the instrumented code
calls an unmanaged, native method that IntelliTest
cannot analyze. If you want IntelliTest to explore
the interaction of both, you must mock the unmanaged method.

<a name="uninstrumentable-method-called"></a>
## Uninstrumentable method called

IntelliTest [generates test inputs](input-generation.md)
by monitoring execution of .NET applications. However,
there are some methods that, for technical reasons,
IntelliTest cannot monitor . For example, IntelliTest
cannot monitor a static constructor.

This warning appears when the instrumented code calls a method that IntelliTest cannot monitor.

<a name="testability-issue"></a>
## Testability issue

IntelliTest [generates test inputs](input-generation.md) by monitoring the program execution. It can only generate relevant test inputs when the program is deterministic, and when the relevant behavior is controlled by the test inputs.

This warning appears because, during execution of your
test case, a method was called that either behaves
non-deterministically, or interacts with the
environment. Examples are methods of
**System.Random** and **System.IO.File**. If you want
IntelliTest to create meaningful test inputs, you
must mock the methods that IntelliTest flags as
testability issues.

<a name="limitation"></a>
## Limitation

IntelliTest [generates test inputs](input-generation.md)
by using a [constraint solver](input-generation.md#constraint-solver).
However, there are some operations that are beyond
the scope of the [constraint solver](input-generation.md#constraint-solver).
This currently includes:

* most floating point operations (only some linear arithmetic is supported on floating point numbers)
* conversions between floating point numbers and integers
* all operations on the **System.Decimal** type

This warning appears when the executed code performs
an operation or calls a method that IntelliTest
cannot interpret.

<a name="observed-call-mismatch"></a>
## Observed call mismatch

IntelliTest [generates test inputs](input-generation.md)
by monitoring program execution. However, IntelliTest
might not be able to monitor all instructions. For
example, it cannot monitor native code, and it
cannot monitor code that is not instrumented.

When IntelliTest cannot monitor code, it cannot
generate test inputs that are relevant to that code.
Often, IntelliTest is not aware of the fact that it
cannot monitor a method until a call to that method
returns. However, the cause of this warning is:

* IntelliTest monitored some code, which initiated a call to an uninstrumented method
* The uninstrumented method called a method that is instrumented
* IntelliTest monitors the instrumented method that was called

IntelliTest does not know what the uninstrumented
intermediate method did, so it might not be able to
generate test inputs that are relevant to the
nested instrumented call.

<a name="value-static-field"></a>
## Value stored in static field

IntelliTest can systematically determine
[relevant test inputs](input-generation.md) only when the
unit test is deterministic; in other words, it always
behaves the same way for the same test inputs. In
particular, this means that the test should leave the
system in a state that allows to re-execute that test.
Ideally, the unit test should not change any global
state, but all interactions with globals should be mocked.

This warning indicates that a static field was changed; this might make the test behave non-deterministically.

In some situations, changing a static field is acceptable:

* when the test inputs causes setup or cleanup code to undo the change
* when the field is initiated only once, and the value does not change afterwards

<a name="report-bug"></a>

## Got feedback?

Post your ideas and feature requests on [Developer Community](https://developercommunity.visualstudio.com/content/idea/post.html?space=8).