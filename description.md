# Background
An equality graph (E-graph) is a data structure which effectively
stores equivalence relation betweeen terms of a formal language. Such
a data structure is used for a program optimization technique called
equality saturation. The idea is to repeatly apply pattern-nased
rewrites on terms of a input string and adding them to the E-graph
till a fixed-point is reached, i.e. till the equality saturation is
reached. Finally extraction is performanced where using an heuristic
to find an optimal way of rewriting the input string.

There are many engines which perform this process in a highly
sequential or concurrent manner. These approaches are ill-fitted for
GPUs, they are organized into many small threads which are have a slow
clock frequency and poorly interleaves concurrently. Hence, the lack
of exisiting E-graph implementations meant for GPUs.

# Motivation
The ability to express equality saturation with E-graphs on a GPU
would be benefecial due to the fact that GPUs more effeciently uses
transistors to get higher performance than CPUs. Futhermore, parallel
architectures do not suffer from the problem of needing good single
core performance which leads to the need for dissipating large amounts
of heat. So in an ideal world we would be able to map any algorithm
efficiently to GPU. 

# Problem Statement
The problem is: "if you are able to map E-graphs efficiently to GPU as
to be able to perform equality saturation". The manner this will be
done is using a data-parallel programming approach since it is a easy
mental model and maps easily to a GPU.
