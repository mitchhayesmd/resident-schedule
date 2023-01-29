# resident-schedule
Resident vacation and call schedule solver 

Assigns vacation weeks to 12 residents in our Urology program as well as weekend call for three combined call pools (OHSU, VA, peds).  

Each resident gets 4 weeks of vacation. The total number of weekend call shifts (and call shifts during holidays) depends on your year (PGY2 through PGY5). 

There are two residents on call every weekend and all weekends must be covered.
      a. One resident takes the longer call, Friday night (about 12 hours) and 24 hour call on Sunday 
      b. The other takes one 24 hour shift on Saturday 

Some vacations are taken during rotations outside of the call pool. Thus, these are not scheduled. 
      a. There are 6 full time residents in the call pool, 3 residents who spend 8 months in the call pool, and 3 residents who spend 6 months in the call pool.
      b. That is 6x12 + 3x8 + 3x6 = 114 resident-months in the call pool (out of a total 12*12 = 144 resident-months in the call pool). 
      c. Thus, there are (114/144)x48 = 38 vacations that need to be scheduled in this problem.

There are three main rotations to consider in the pool (OHSU, VA, peds). The time spent on each rotation is 4 months. 
      a. PGY2s spend a single 4 month rotation on each service. 
      b. PGY3s have two separate 2 month rotations on the VA service. They also have one 2 month research block which is in the call pool as well, but belongs to no service.
      c. PGY4s spend one 4 month rotation on peds and one on OHSU. 
      d. PGY5s have two separate 4 month rotations on OHSU, and one 4 month rotation on VA. 

There are multiple constraints: 
  1. No two residents can take vacation at the same time with one exception: 
      a. PGY5 ('chief' residents) have the option to use the last week in June for vacation, even if the other chiefs are also gone. 
  2. Vacation weeks must be distributed evenly amongst the three services (proportional to the total resident-months owned by the service). 
      a. There are 4 full time residents on the OHSU service, 3 full time residents on the VA service, and 2 full time residents on the peds service.
      b. Thus the number of allocated vacations for each service is 16, 12, and 8 (and the number allocated to the 2 month research block is 2, so a total of 38 as stated above).
      c. In an attempt to simplify things, we asked that resident classes (groups of 3) decide amongst themselves who would take 2 weeks of vacation on each service. 
      d. Thus, each resident would take at least one week of vacation on each of the 4 month blocks, and 1/3 residents would take a second week during prespecified mutually exclusive rotations.
  3. Vacations cannot be taken during specific times. 
      a. No one can take vacation during July or around the time of major conferences (WSAUA, AUA). 
      b. PGY2-4s cannot take vacation the last week of June (as PGY5 residents might be gone and all hands on deck are needed). 
  4. To allow maximum vacation time, no weekend call will be scheduled around the time of vacation. 
  5. PGY2s do not take weekend call for the first two months of the year.
  6. PGY2s should be paired with a senior resident (PGY4 or 5) for the first 6 months (except during specific holiday calls). 
  7. Senior residents do not take Thanksgiving, Xmas, or NYE call. 
  8. Senior residents do not take weekend call during major conferences. 
  9. Holidays are counted separately. They are the 4th of July, Labor Day, Thanksgiving, Xmas, NYE, MLK, President's, and Memorial day. The two shift lengths depends on the holiday but are at least 36 hours and up to 48 hours. 
  10. The number of holiday calls defined by PGY is as follows: 
      a. PGY 3 and 5s: 1 holiday call (3s are in the call pool for 6 months, 5s are in the call pool for 12 months) 
      b. PGY 4s: 1-2 holiday calls (4s are in the call pool for 8 months) 
      c. PGY 2s: 2 holiday calls (2s are in the call pool for 12 months) 
  11. The total number of calls defined by PGY is as follows: 
      a. PGY 4/5: 8 calls 
      b. PGY 3: 7 calls 
      c. PGY 2: 12 calls 
  12. The minimum number of non-holiday Friday/Sunday calls defined by PGY is as follows: 
      a. PGY 5: 1 call 
      b. PGY 4: 2-3 calls 
      c. PGY 3: 3 calls 
      d. PGY 2: 8 calls 
  13. (So FYI breaking down the total call burden from PGY 2 to 5 is as follows:) 
      a. PGY 5: (36-48)*1 (holiday call) + 36*1 (Fri/Sun call) + 24*6 (Sat call) = about 216-228 hours over 12 months = 18-19 hours per month 
      b. PGY 4: (36-48)*(1-2) + 36*(2-3) + 24*(3-5) = 228- 264  over 8 months = 28.5-33 hours per month 
      c. PGY 3: (36-48)*1 + 36*3 + 24*3 = 216-228 over 6 months = 36-38 hours per month 
      d. PGY 2: (36-48)*2 + 36*8 + 24*2 = 408-420 over 12 months = 34-35 hours per month 
 
 
