## PROBLEM: 

        Problem: Fish in the River
        [2,3]  A : size of the fish 
        [0,1]  B : indications on swimming movement : 0 : upstream , 1: downstream. 

        You are given two non-empty arrays A and B representing N voracious fish in a river, ordered from upstream to downstream. 
        Array A contains the sizes of the fish, and array B contains the directions (0 for upstream, 1 for downstream) of the fish. 
        If two fish move in opposite directions and there are no other (living) fish between them, they will eventually meet each other. 
        Compute the number of fish that will stay alive.

        For example, given the arrays A = [4, 3, 2, 1, 5] and B = [0, 1, 0, 0, 0], the function should return 4, as four fishes 
        (4,2,1,5) will stay alive.

## ALGORITHM

        0. Create a function that receives both arrays, define a counter and a list of fishes headed upstream
        1. Iterate through the second array to see if any fish is moving in opposite direction.
        2. Store the fish moving upstream in an array us if B[i] == 0
        3. If the fish is moving downstream, check the last element that was added to us. It will either eat
            the fish or be eaten
        4. Implement a while loop to continuously check. If the last fish appended in us eats the current fish. 
            Increment the counter, if it is eaten, pop the appended fish and the while loop checks again against
            last fish in upstream fish until the condition is fulfilled
        5. Return the difference between original length of fishes passed and eaten fish