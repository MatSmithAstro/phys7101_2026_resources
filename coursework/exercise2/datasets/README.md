# Exercise 2 datasets

From the **Fantasia Database** on PhysioNet (version 1.0.0): 40 healthy adults, 20 young (21–34) and 20 elderly (68–85), lying at rest while watching the film *Fantasia*, with ECG and breathing recorded. <https://physionet.org/content/fantasia/1.0.0/>

For this exercise we kept minutes 30–60 of each record and used the database's own beat annotations.

- **`fantasia_beats.csv`**: `subject`, `t_s`: the time (s) of every annotated heartbeat, including ectopic (extra) beats.
- **`fantasia_resp.csv`**: `subject`, `t_s`, `resp`: the breathing signal (arbitrary units), resampled to 4 samples per second. Short gaps were filled linearly; one person has a gap of more than 1 s, left as NaN.
- **`fantasia_subjects.csv`**: `subject`, `group` (young or elderly), and the age and sex given in the database.

**Please cite** both of these whenever you use the data:

- N. Iyengar, C.-K. Peng, R. Morin, A. L. Goldberger and L. A. Lipsitz (1996), "Age-related alterations in the fractal scaling of cardiac interbeat interval dynamics", *Am. J. Physiol.* **271**, R1078–R1084.
- A. L. Goldberger *et al.* (2000), "PhysioBank, PhysioToolkit, and PhysioNet: components of a new research resource for complex physiologic signals", *Circulation* **101**, e215–e220.

The data are de-identified and openly available; the licence and terms are on the PhysioNet page above.
