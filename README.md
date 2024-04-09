# Time-Needed-to-Buy-Tickets
There are n people in a line queuing to buy tickets, where the 0th person is at the front of the line and the (n - 1)th person is at the back of the line.  You are given a 0-indexed integer array tickets of length n where the number of tickets that the ith person would like to buy is tickets[i].  Each person takes exactly 1 second to buy a ticket. 

class Solution:
    def timeRequiredToBuy(self, tickets: List[int], k: int) -> int:
        total = 0

        for i, x in enumerate(tickets):
            if i <= k:
                total += min(tickets[i], tickets[k])
            else:
                total += min(tickets[i], tickets[k] - 1)

        return total
