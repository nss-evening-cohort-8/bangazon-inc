# Kill Nickelback

In this exercise, you're going to use HashSets, Tuples, and Lists.

## Setup

```
mkdir -p ~/workspace/csharp/exercises/nickelback && cd $_
dotnet new console
dotnet add package System.ValueTuple
dotnet restore
```

## Instructions

1. Define a class called `Song` that has a string property `Artist` and a string property `Name`.  Both properties should be required (invariant) in order to construct an instance of `Song` 
1. Define a List, named `goodSongs`, that will hold instances of `Song`.
1. Define a HashSet, named `allSongs`, that contains 7 instances of `Song`.

    Make sure that some of the songs are from the band Nickelback. You can see a [list of their greatest hits](https://www.amazon.com/Best-Nickelback-1/dp/B00FFERTUK/) on Amazon.
1. Once the set is populated with 7 instances, iterate over the set of songs, and check if the band name is "Nickelback".
1. If the band is **not** Nickelback, then add it to the `goodSongs` list.
1. Use another `foreach` loop to print out all the good songs.
