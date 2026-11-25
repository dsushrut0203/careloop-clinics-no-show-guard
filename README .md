# CareLoop Clinics — No-Show Guard

**GitHub Repository:** https://github.com/dsushrut0203/careloop-clinics-no-show-guard.git

## Project Summary

- **Part 1 — Python & Data Foundations:** Cleaned the original 1,020 appointment records to produce `appointments_clean.csv` containing 990 rows and 16 columns.
- **Part 2 — SQL Analysis:** Analysed 990 appointments across 8 clinics; the no-show rate reached 60.5% for bookings made 31+ days ahead, compared with 16.2% for bookings made 1–7 days ahead.
- **Part 3 — Machine Learning:** Selected Logistic Regression, which achieved the highest mean cross-validation ROC-AUC of 0.774 and a test ROC-AUC of 0.789.
- **Part 4 — GenAI Analysis:** Analysed 10 follow-up notes: 9 valid responses and 1 skipped blank note. Both forgotten/no-reminder notes were associated with appointments where no reminder was recorded.

## Business Recommendation

CareLoop Clinics should introduce a risk-based appointment follow-up process that prioritises patients most likely to miss their appointments. The cleaned dataset contains 990 appointments across 8 clinics, including 218 no-shows. SQL analysis identified a 60.5% no-show rate among appointments booked 31 or more days in advance, compared with 16.2% among appointments booked 1–7 days ahead. Logistic Regression achieved a test ROC-AUC of 0.789, with a classification threshold of 0.35, recall of 0.571 and precision of 0.571; it flagged 49 of the 198 test appointments for follow-up. In the GenAI analysis, 5 of the 10 reviewed appointments had no reminder recorded, and both notes classified as forgotten appointments were linked to appointments without a recorded reminder. CareLoop should prioritise reminder verification, accurate patient contact details and targeted calls for higher-risk appointments. These recommendations should be evaluated through a future pilot because the small follow-up-note sample and observational data do not establish causation.

## Selected Model and Evaluation

**Selected model: Logistic Regression**

Logistic Regression was selected because it achieved the highest mean cross-validation ROC-AUC among the evaluated models.

- Mean cross-validation ROC-AUC: 0.777
- Test ROC-AUC: 0.789
- Classification threshold: 0.35
- Test accuracy: 0.788
- Test precision: 0.571
- Test recall: 0.571
- Test F1-score: 0.571
- Test appointments flagged: 49 out of 198

The threshold of 0.35 was selected to improve the identification of potential no-shows while balancing the number of appointments requiring follow-up.

## Limitations

1. The 10 follow-up notes are an illustration and cannot show the actual reasons for missed appointments across all clinics.
2. The train/test split was random rather than past-to-future, so the evaluation may not fully represent performance on future appointments.
3. The data are observational, so associations between reminders and no-shows do not prove that reminders cause a reduction in missed appointments.

## Conclusion

The project combines data cleaning, SQL analysis, machine learning and GenAI-assisted follow-up-note classification to help CareLoop Clinics understand appointment no-shows and identify appointments requiring attention. A risk-based follow-up and reminder-verification process is recommended for further evaluation.
