# School District Analysis
Analyzing test score data for a school district

## Overview
The purpose of this analysis is to assess the impact that a school's size, type (district vs charter), and funding (on a per student basis) has on student academic performance (specifically in Math & Reading test scores). 


## Results
#### Note: Due to the evidence of academic dishonesty that was identified at Thomas High School ("THS"), the Math and Reading scores for the entire ninth grade class at THS has been nullified. The impact to the analysis is summarized below:
1. The district summary is negatively impacted by the removal of THS 9th grade test scores. We can see the Average Math Score decreasing slightly and the 'pass' rates of students in math, reading, and overall, each experience a minor drop.

    - Includes THS 9th Graders:
![dist_summ_pre_scandal](https://user-images.githubusercontent.com/97985062/154777484-a130beef-5111-498b-b276-09717066f6e0.png)
    - Excludes THS 9th Graders:
![dist_summ_post_scandal](https://user-images.githubusercontent.com/97985062/154777231-f162b783-b12f-4ca0-bf15-e5023e77e95b.png)


2. The school summary for experienced the greatest impact from dropping THS 9th graders. The THS average scores and pass rates dropped drastically once the 9th graders were excluded. As a result, we needed to modify the analysis to take into account that we had nullified the 9th grader data for THS. The revised dataframe (specifically for THS) is presented below.

    - Original DataFrame:
![school_summ_pre_scandal](https://user-images.githubusercontent.com/97985062/154777236-1a0cc104-f5e0-49f7-86ef-764244ee21e9.png)

    - Updated DataFrame excluding THS 9th Graders:
![school_summ_post_scandal](https://user-images.githubusercontent.com/97985062/154777240-33a371f3-68f9-41d1-bee3-4c1cca90afd7.png)

    - Revised DataFrame for THS, ignoring 9th Grade data:
![school_summ_post_scandal_ths_revised](https://user-images.githubusercontent.com/97985062/154777243-b680fc10-7661-41b1-8119-dd06ef7239b9.png)

3. Thankfully, this change did not actually result in a material change to THS' standings against other schools, with THS continuing to place second in terms of the percentage of students passing both subjects overall.

    - Revised list of top 5 schools:
![top_schools_post_scandal](https://user-images.githubusercontent.com/97985062/154777277-1af81c4c-d275-4cad-9182-37ecedd3c556.png)


4. The removal of 9th grade scores for THS did not materially impact the rest of our analysis.
    - Math & Reading Scores by grade did not change other than a NaN ("null") value appearing for THS in the 9th grade column in each DataFrame.
    - The analysis of scores by school spending was un-changed (after rounding). However, when we dug deeper, we saw that the $630-644 (per student) bucket showed a slightly lower average math score and overall pass rates (due to THS belonging to this bucket).
    - The analysis of scores by school size was similarly un-changed (after rounding). Similary, when we dug deeper, we saw that the 1000-2000 (size) bucket showed a slightly lower average math score and overall pass rates (due to THS belonging to this bucket).
    - The analysis of scores by school type was similarly un-changed (after-rounding). Again, when we dug depeer, we saw that the charter school bucket showed a slightly lower average math score and overall pass rates (due to THS being a charter school).

## Summary
The removal of THS grade 9 test scores resulted in the following changes to the overall analysis:
1. We needed to re-perform the count of "valid" data point (to exclude THS 9th graders). This became the new denominator when calculating the pass rates in math/reading/overall.
2. After removing the "invalid" datapoints from the student data, we needed to re-calculate & update the average scores and pass rates for all subsequent analysis that were based on the student data.
3. Specifically for THS, we needed to reclculate all averages using only 10th, 11th, and 12th grade data. 
4. In the revised analysis, we see that the impact of removing THS 9th grade data had an immaterial negative impact to average math scores, % of students passing math, % students passing reading, and % students passing overall for the bucket corresponding to THS, when looking at various school attributes (school funding, size, and type).