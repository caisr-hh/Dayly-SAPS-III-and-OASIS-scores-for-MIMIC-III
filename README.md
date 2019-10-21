# Dayly-SAPS-III-and-OASIS-scores-for-MIMIC-III
Used in the Thesis: Towards Understanding ICU Procedures using Similarities in Patient Trajectories.
SAPS-III and OASIS score quarries computed dayly. Existing code from the offical MIMIC-III repository was modified to achieve this. 
The original MIMIC-III repository can be found here: https://github.com/MIT-LCP/mimic-code

This includes modefied queries required for the severity score computations, such as:
aterial blood gas, laboratory measurements, urine-output, etc.
Each query generates a materialized view, allowing simply sequential execution of the querries to compute the scores.
Comments in the querry files are unchanged and are identical to the original files found in the offical repository.

NOTE: OASIS scores are only computed for ICU-stays up to 30-days, this can be changed easily be modifying the line 47
in oasis-all-day.sql:

 and se.transfertime < ie.intime + interval '30' day
 
for example, up to 80 days:
 
 and se.transfertime < ie.intime + interval '80' day


