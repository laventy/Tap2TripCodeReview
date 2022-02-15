# Tap2TripCodeReview

## Overall Solution

The matching algorithm used from candidate is to brute-force all matches for a given tap, with the downside on performance if there are huge number of entries (**O(n^2)**).

Depending on assumptions and requirements, going through the tap list **linearly** (**O(n)**) may be able to output trips.

Let us say if the taps are sorted by time i.e. the oldest being top in the CSV. Given an ideal situation, considering the first tap (`ON`) at the top and getting the next one,

1. if the next one is `ON`, then consider a `Incomplete Trip`. (given that can only tap-on once on a single trip)
2. if the next one is `OFF` at different stop, then consider a `Complete Trip`. (given that can only tap-off once on a single trip)
3. if the next one is `OFF` at same stop, then consider a `Cacelled Trip`. (given that can only tap-off once on a single trip)
4. consider the third one and continue the same process...

The solution above is an example of an ideal situation. However, I think linear complexity is possible given that the structure of tap CSV is subject to assumptions.

## Code Quality

1. Strong feeling of quite well-organised and readable code. Easy to follow the logic flow due to easy-to-understand naming for functions and variables.
2. By saying well-organised, the codebase is divided into meaningful parts. i.e. services, interfaces, constants, helpers, models etc.
3. Get good coverage of unit testing.

## Extendability
1. The candidate uses the interface quite well so it is easy to create another instance following the interface without making any major code changes.
