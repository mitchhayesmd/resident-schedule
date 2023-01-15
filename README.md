# resident-schedule
Resident vacation and call schedule solver 

Assigns vacation weeks to 12 residents in our Urology program as well as weekend call for three combined call pools (OHSU, VA, peds).  

Each resident gets 4 weeks of vacation. The total number of weekend call shifts (and call shifts during holidays) depends on your year (PGY2 through PGY5). 

There are two residents on call every weekend and all weekends must be covered.

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
  1. No resident can take vacation at the same time with one exception: 
      a. PGY5 ('chief' residents) have the option to use the last week in June for vacation, even if the other chiefs are also gone. 
  2. Vacation weeks must be distributed evenly amongst the three services (proportional to the total resident-months owned by the service). 
      a. There are 4 full time residents on the OHSU service, 3 full time residents on the VA service, and 2 full time residents on the peds service.
      b. Thus the number of allocated vacations for each service is 16, 12, and 8 (and the number allocated to the 2 month research block is 2, so a total of 38 as stated above).
      c. In an attempt to simplify things, we asked that resident classes (groups of 3) decide amongst themselves who would take 2 weeks of vacation on each service. 
      d. Thus, each resident would take at least one week of vacation on each of the 4 month blocks, and 1/3 residents would take a second week during prespecified mutually exclusive rotations.
  3. Vacations cannot be taken during specific times. 
      a. No one can take vacation during July or around conferences. 
      b. PGY2-4s cannot take vacation the last week of June (as PGY5 residents might be gone and all hands on deck are needed). 
  4. To allow maximum vacation time, no weekend call will be scheduled around the time of vacation. 
  5. PGY2s do not take weekend call for the first two months of the year.
  6. PGY2s should be paired with a senior resident (PGY4 or 5) for the first 6 months (except during specific holiday calls). 
 
