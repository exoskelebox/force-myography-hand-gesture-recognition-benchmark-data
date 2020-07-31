
# Force myography benchmark data for hand gesture recognition and transfer learning

A force myography hand gesture benchmark dataset collected using a [commercially available sensor setup](https://www.bioxgroup.dk/products-biox-armband/) from 20 persons covering 18 unique gestures. We hope the benchmark data will facilitate the comparison among different hand gesture recognition algorithms. In addition, when considering different persons as different domains or tasks, it can also work as a benchmark dataset for evaluating transfer learning and multi-task learning. The code related to our data collection process, can be found in the repository [data-collection](https://github.com/exoskelebox/data-collection).

## Structure

All dataset files are provided as related CSV files. The structure of each file is described in detail below. The files all contain a column named **subject_id**, a unique identifier which anonymously identifies a subject, which acts as a relational property.

### Subjects

The subjects file contains a row of subject related contextual information for each subject.

| column name                   | description                                                                                                         |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| subject_id                    | A numeric identifier of the subject.                                                                                    |
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
| subject_id                   | A numeric identifier of the subject.                                                          |
| wrist_calibration_iterations | A numeric indication of the number of calibration steps taken to calibrate the wrist sensors. |
| arm_calibration_iterations   | A numeric indication of the number of calibration steps taken to calibrate the arm sensors.   |
| wrist_sensor_[1-7]           | A series of numeric values from the wrist sensors at the final wrist calibration step.        |
| arm_sensor_[1-8]             | A series of numeric values from the arm sensors at the final arm calibration step.            |

### Sensor readings

The data file contains rows of sensor readings for each gesture.

| column name        | description                                                                                  |
| ------------------ | -------------------------------------------------------------------------------------------- |
| subject_id         | A numeric identifier of the subject.                                                         |
| repetition         | A numeric indication unique to a subject of the number of times a gesture has been repeated. |
| timestamp          | An indication of the time, down to the microsecond, a reading was captured. As the reference point is undefined, only the relative time between samples is valid.  |
| wrist_sensor_[1-7] | A series of numeric values from the wrist sensors at the time of capture.                    |
| arm_sensor_[1-8]   | A series of numeric values from the arm sensors at the time of capture.                      |
| gesture            | An indication of the gesture that was performed.                                             |

# Use case
Code related to a number of model implementations trained on the benchmark dataset provided here can be found in the repository [model-training](https://github.com/exoskelebox/model-training).  Using the dataset, we trained three differently configured fully connected neural networks (FCNN), progressive neural networks (PNN) and combined progressive neural networks  (CPNN) for each subject and used the average accuracy of the models as a scoring metric. The results of which, can be seen in the table below.
 
|Dense 1|Dense 2|Dense 3|Dropout|FCNN    |CPNN    |PNN    |
|-------|-------|-------|-------|--------|--------|-------|
|256    |-      |-      |0.4    |77.59%  |78.12%  |76.65% |
|256    |32     |-      |0.1    |77.81%  |78.28%  |75.42% |
|256    |64     |32     |0.3    |78.14%  |77.11%  |76.27% |

# License

Neither Aalborg University nor any of the researchers involved can guarantee the correctness of the data, its suitability for any particular purpose, or the validity of results based on the use of the data set. The data set may be used for any research purposes under the following conditions:

1.  The user may not state or imply any endorsement from Aalborg University or the researchers who produced it.
2.  The user must acknowledge the use of the data set in publications resulting from the use of the data set (see the Citation section for details.).
3.  The user may redistribute the data set, including transformations, so long as it is distributed under these same license conditions.
4.  The user may not use this information for any commercial or revenue-bearing purposes without first obtaining permission from a faculty member of the Department of Computer Science at Aalborg University.
5.  In no event shall Aalborg University, its affiliates or employees be liable to you for any damages arising out of the use or inability to use these programs (including but not limited to loss of data or data being rendered inaccurate).

# Citation

If you use the benchmark data for your research, please cite the following paper. 
<pre>     
@misc{andersen2020force,
  title={Force myography benchmark data for hand gesture recognition and transfer learning},
  author={Thomas Buhl Andersen and Rógvi Eliasen and Mikkel Jarlund and Bin Yang},
  year={2020},
  eprint={2007.14918},
  archivePrefix={arXiv},
  primaryClass={cs.LG}
}
</pre>   
