Individuals from Isotopes: Can Stable Isotopes Distinguish the Remains of 
Different Cooper’s Hawks (*Astur cooperii*)?
--------------------------------------

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><strong>Corresponding Author:</strong>
Jonathan Dombrosky</td>
<td align="left"><strong>Contact:</strong>
jdombrosky at crowcanyon.org</td>
</tr>
</tbody>
</table>

Dombrosky, J., M. LaZar, C. Hyland, and S. D. Newsome. Individuals from 
Isotopes: Can Stable Isotopes Distinguish the Skeletal Remains of Different 
Cooper’s Hawks (*Astur cooperii*)? To be submitted to Journal of Archaeological 
Method and Theory.

There are two folders and three Quarto files in this repository. The first
folder, `data`, includes only one file. It is .txt file that has all the raw
data necessary to reproduce the analytical figures and tables provided in 
the manuscript. The columns provided in this file are:

  **MSB_Number:** This is the Museum of Southwestern Biology (MSB) Specimen number
  
  **Individual:** The individual number (1-20) arbitrarily assigned to each
  individual Cooper's Hawk specimen by increasing MSB Number.
  
  **Tissue:** Pertains to whether the observation derives from bone, muscle, or 
  liver.
  
  **Element:** If the observation is from bone tissue, this column specifies what
  skeletal element the observation is. It can be either humerus, ulna, femur, 
  tibiotarsus, rib, or pygostyle.
  
  **Side:** If the observation is from bone tissue, this column specifies what 
  side of the bird the skeletal element derives from (right or left). Bones that
  were not sided or where they are axial skeletal elements are given NA.
  
  **Bone_Type:** If the observation is from bone tissue, this column indicates 
  what category of bone the skeletal element is by how it grows. The options are
  long, flat, or irregular.
  
  **d13C:** Provides the delta carbon-13 value for each observation expressed in
  per mille.
  
  **d15N:** Provides the delta nitrogen-15 value for each observation expressed 
  in per mille.
  
  **d2H:** Provides the delta two H value for each observation expressed in per 
  mille.
  
  **CN:** This column provides carbon-to-nitrogen ratios for each observation. 
  Importantly, these are given as mass ratios and not atomic ratios. Converting
  to atomic ratios is easy enough. In `mutate()` function form, it looks like:
  `mutate(CNatomic = CN * (14/12))`.

The `figs` folder is where all of the main and supplemental figures are stored. 

The only manuscript element that cannot be reproduced is Table 1, which is of 
metadata about each raptor individual we sampled for stable isotope analysis. 

Quarto file 1, `1_exploratory_data_analysis.qmd`, corresponds with all the 
results and figures mentioned in section 4.1 (as well as providing the code
to reproduce the conceptual diagrams borrowed from the ecological literature in
Figure 1). This file should run relatively quickly. However, there is a 
resampling function used to generate Figure 4 that might slightly slow things
down.

Quarto file 2, `2_sampling_overlap.qmd`, corresponds with all the results and
figures mentioned in section 4.2 of the manuscript.
This file is a little more computationally intensive, but should not take too 
long to run (on the order of 10 or so minutes perhaps). This is where all the
elliptical overlap calculations are run, which requires a little oomph.

Quarto file 3, `3_predictive_moderling.qmd`, corresponds with all the results
and figures mentioned in section 4.3 of the manuscript. This is the most
computationally intensive file provided. This is where the different machine
learning algorithms are tuned and applied. It should take 30 or so minutes to
run.