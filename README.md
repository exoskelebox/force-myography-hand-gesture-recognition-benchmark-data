# Force Myography Hand Gesture Recognition Benchmark Data

A benchmark dataset collected using a [commercially available sensor setup](https://www.bioxgroup.dk/products-biox-armband/) from 20 persons covering 18 unique gestures.

## Structure

All dataset files are provided as related CSV files. The structure of each file is described in detail below. The files all contain a column named **subject_id**, a unique identifier which anonymously identifies a subject, which acts as a relational property.

### Subjects

The subjects file contains a row of subject related contextual information for each subject.

| column name                   | description                                                                                                         |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| subject_gender                | An indication of subject gender.                                                                                    |
| subject_age                   | A numeric indication of subject age.                                                                                |
| subject_fitness               | A numeric indication of subject fitness i.e. the number of days a week where the subject exercises for 30+ minutes. |
| subject_handedness            | A boolean indication of subject handedness.                                                                         |
| subject_impairment            | A boolean indication of whether the subject had any physical impairments that might effect hand gestures.           |
| subject_wrist_circumference   | A floating point measure of the subjects wrist circumference.                                                       |
| subject_forearm_circumference | A floating point measure of the subjects forearm circumference.                                                     |

### Calibration

The calibration file contains a row of calibration data for each subject.

| column name                  | description                                                                                   |
| ---------------------------- | --------------------------------------------------------------------------------------------- |
| wrist_calibration_iterations | A numeric indication of the number of calibration steps taken to calibrate the wrist sensors. |
| arm_calibration_iterations   | A numeric indication of the number of calibration steps taken to calibrate the arm sensors.   |
| wrist_sensor_[1-7]           | A series of numeric values from the wrist sensors at the final wrist calibration step.        |
| arm_sensor_[1-8]             | A series of numeric values from the arm sensors at the final arm calibration step.            |

### Sensor readings

The data file contains rows of sensor readings for each gesture.

| column name        | description                                                                                  |
| ------------------ | -------------------------------------------------------------------------------------------- |
| repetition         | A numeric indication unique to a subject of the number of times a gesture has been repeated. |
| timestamp          | An indication of the time of day, down to the nanosecond, a reading was captured.            |
| wrist_sensor_[1-7] | A series of numeric values from the wrist sensors at the time of capture.                    |
| arm_sensor_[1-8]   | A series of numeric values from the arm sensors at the time of capture.                      |
| gesture            | An indication of the gesture that was performed.                                             |

# License

Neither Aalborg University nor any of the researchers involved can guarantee the correctness of the data, its suitability for any particular purpose, or the validity of results based on the use of the data set. The data set may be used for any research purposes under the following conditions:

1.  The user may not state or imply any endorsement from Aalborg University or the researchers who produced it.
2.  The user must acknowledge the use of the data set in publications resulting from the use of the data set.
3.  The user may redistribute the data set, including transformations, so long as it is distributed under these same license conditions.
4.  The user may not use this information for any commercial or revenue-bearing purposes without first obtaining permission from a faculty member of the Department of Computer Science at Aalborg University.
5.  In no event shall Aalborg University, its affiliates or employees be liable to you for any damages arising out of the use or inability to use these programs (including but not limited to loss of data or data being rendered inaccurate).
