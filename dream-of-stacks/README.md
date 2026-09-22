# The dream of stacks

Ordinary computation is very good at collapsing things.

Two objects are declared equivalent, so we replace them by one representative.

Several paths lead to the same answer, so we keep the answer and throw away the paths.

A symmetry changes an object without changing what we care about, so we quotient by the symmetry and forget that it was there.

Often that is exactly the right thing to do.

Sometimes it destroys the interesting information.

The dream of stacks is to build programs that can preserve more of the structure of **how things are the same**.

## Sameness can have structure

In algebraic geometry, stacks arise when ordinary quotient spaces are too crude.

If an object has symmetries, it can matter not only that two presentations represent the same underlying thing, but also:

- which transformation identifies them;
- what automorphisms an object has;
- which symmetries stabilize it;
- how local presentations fit together;
- and how the object changes in a family.

Instead of reducing everything immediately to:

~~~text
A = B
~~~

there may be useful information in:

~~~text
A
  -- this identification -->
B
~~~

and in the fact that there may be several different identifications.

The computational question is whether some of that information can remain alive in ordinary programs.

## Do not quotient too early

A program often throws away provenance because the final value is all the next function asks for.

But provenance can matter.

If two search paths reach the same state, were they really interchangeable?

If two coordinate descriptions represent the same geometry, what transformation connects them?

If two colors have the same numerical coordinates in one representation, do they still play the same perceptual role in different contexts?

If two program transformations preserve behavior, what sequence of justified rewrites got from one to the other?

If a fitted model changes under a small perturbation of the data, what family of nearby models are we actually looking at?

These are not all literally algebraic stacks.

The point is to use the mathematics carefully as a guide to representations that retain identifications, symmetries, deformations, and context instead of erasing them at the first opportunity.

## Albers is a motivating collision

[Albers](https://github.com/walnut-burgundy/albers) is one place where this becomes concrete.

A color swatch does not exhaust the phenomenon of color interaction.

The same physical or numerical color can participate differently depending on its surroundings.

That makes color a useful test case for asking what a representation should preserve.

An ordinary data structure may want to store:

~~~text
RGB = (r, g, b)
~~~

A richer experiment may need to remember the presentation in which that color occurred, the neighboring colors, transformations between presentations, and which properties survived those changes.

The point is not to announce that color perception "is a stack."

The point is that stacks provide a rigorous example of mathematics built precisely for situations where context, local presentation, equivalence, and symmetry cannot simply be collapsed away.

## Deformation matters too

There is a second part of the dream.

Do not ask only whether two things are the same.

Ask how one can vary into nearby things.

That leads toward deformation theory, tangent spaces, obstructions, versal families, and moduli.

Computationally, that suggests keeping track of questions like:

- Which changes are genuinely different?
- Which changes are only a change of presentation?
- Which directions of change are possible?
- Which are obstructed?
- Where does sensitivity become large?
- Where does the family become singular?
- Which symmetries appear or disappear at special points?

Those questions occur in geometry, statistics, optimization, programming languages, graphics, and many other places.

## Executable examples before grand theory

The project should not become decorative category theory pasted onto unrelated programs.

The useful path is the opposite:

~~~text
small executable example
    → identify what information ordinary representation loses
    → preserve that information explicitly
    → test the resulting structure
    → only then ask whether the right abstraction is stack-like
~~~

Finite examples are valuable because they can be checked.

A color experiment, a family of roots, a reflection system, a fitted statistical model, or a programming-language transformation can expose one piece of the problem without pretending that the general theory has already been implemented.

The [Stacks Project](https://github.com/one-room-schoolhouse/stacks-project) is retained as a mathematical reference, not as branding for the software.

## The larger ambition

The long-term idea is a kind of computational moduli.

A program would not merely know its current object.

Where useful, it could also retain:

- alternative presentations;
- witnesses of equivalence;
- paths between presentations;
- automorphisms and stabilizers;
- controlled deformations;
- local descriptions;
- and the history by which an identification was made.

That could make programs more inspectable because less of their reasoning would be destroyed by normalization and quotienting.

It could also give language design a richer notion of "the same program" than either literal syntax or one final output.

The dream is not that every program becomes a stack.

The dream is that when sameness has structure, the computer stops throwing that structure away.
