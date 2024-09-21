   # Memorandum of Understanding (Email Summary)

    “Hi,

    This is what came out of our initial scoping meetings with the council:

    **Summary**

    -	Landfill Labs will allow for different scenarios to be analysed and compared.
    -	Within these scenarios, the following will be editable/input:
        o	Historic Landfill Site.
            	Location.
            	Total waste.
        o	Recycling Centres.
            	Location.
            	Generation.
            	Years active.
    -	For a Historic Landfill Site the following are calculated:
        o	Estimated plastic/glass waste.
            	50% of the total, if less than 1250 cubic meters total waste.
            	Otherwise, 30% of the total.
        o	Estimated paper waste.
            	50% of the total.
        o	Estimated metallic waste.
            	0% of the total if less than 1250 cubic meters total waste.
            	Otherwise, 20% of the total.
    -	The “location” doesn’t need to be exact. The map is modelled as 3 zones:
        o	A, B, and C.
        o	Travelling between zone A and B takes 2 hours (and vice versa).
        o	Travelling between zone A and C takes 4 hours (and vice versa).
        o	Travelling between zone B and C takes 3 hours (and vice versa).
        o	Travelling within a zone takes 1 hour (for a return trip).
    -	Waste should be measured in cubic meters (all types).
    -	Recycling centres have different “Generation”(s).
        o	Alpha: Processes at 1 cubic meter(s) per hour for all waste types. 
        o	Beta: Processes at 1.5 cubic meter(s) per hour for all waste types.
        o	Gamma:
            	Processes at 1.5 cubic meter(s) per hour for plastic and glass types.
            	Processes at 2.0 cubic meter(s) per hour for metallic types.
            	Processes at 3.0 cubic meter(s) per hour for paper types.
    -	In any given scenario, a single truck capable of carrying 20 cubic meters of waste (regardless of type) transports waste from the historic site to a recycling centre that is considered both viable and optimal:
        o	A recycling centre is considered viable if it can be travelled to within 3 hours. Additionally, if a historic site does not contain any metallic waste only recycling centres with generations of alpha and beta are considered viable.
        o	An optimal recycling centre is determined based on its location (or distance to the historic site), generation, and the number of years it has been active (and in that order).
    -	The truck will always make a return trip.
    -	After the truck has transported the waste to the optimal recycling centre, the waste is processed at a rate defined by the recycling centres generation.
    -	Thus, the following times/durations will be output from any given scenario:
        o	Travel duration (in hours).
        o	Process duration (in hours).
        o	Total duration (in hours).

    **Worked example**

    1.	Given a scenario in which:
        o	There is a historic location with:
            	Location: A.
            	Total waste: 5000 cubic meters.
        o	And 3 recycling centres:
            	Recycling centre #1 with:
                •	Location: A.
                •	Generation: Alpha.
                •	Years active: 10.
            	Recycling centre #2 with:
                •	Location: B.
                •	Generation: Beta.
                •	Years active: 8.
            	Recycling centre #3 with:
                •	Location: C.
                •	Generation: Gamma.
                •	Years active: 12.

    2.	Estimated quantities for the different types of waste in the historic landfill site should be calculated as follows:
        o	Total waste is greater than 1250 cubic meters so we can assume:
            	50% is paper waste.
            	30% is plastic waste.
            	20% is metallic waste.
        o	So, there is an estimated:
            	5000 * 0.5 = 2500 cubic meters of paper waste.
            	5000 * 0.3 = 1500 cubic meters of plastic waste.
            	5000 * 0.2 = 1000 cubic meters of metallic waste.

    3.	The following recycling centres can be travelled to within 3 hours and are therefore considered viable:
        o	Recycling centre #1.
        o	Recycling centre #2.

    4.	Recycling centre #1 would be considered optimal because it is nearest to the historic site (Note that this is true despite recycling centre #2 being a newer generation. Distance/travel time to historic site is considered first, then generation, and then years active).

    5.	The time to fill the recycling centre is: 5000 cubic meters / 20 cubic meters per transport = 250 round trips. With each round trip being a single hour in this case, the travel duration is: 250 trips * 1 hour per trip = 250 hours.

    6.	The time to process the waste after delivery (i.e., process duration) is: 5000 cubic meters / 1 cubic meter processed per hour = 5000 hours.

    7.	The total duration is therefore: 5000 hours + 250 hours = 5250 hours.

    **Other notes**

    Additionally, they were keen we acknowledge that the data stored in the system is commercially sensitive. They are also keen that the system be generally performant.

    Based on all this I put together a spec, including some architecture diagrams and a flowchart that shows the logic for running the different scenarios. All of these have been signed-off by the council, now they’re waiting for your test plan.

    Kind regards,
    Sam”
