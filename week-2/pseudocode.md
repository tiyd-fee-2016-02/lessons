# Pseudo Code

Pseudo code is fake code. It's often helpful to break a problem down without
actually writing real code.


---

## The Challenge

How would you tell a computer to make toast from scratch?

Assumptions / resources:

- Flour
- Water
- Yeast
- Bowl
- Measuring tools
- Knives
- Oven
- Toaster
- Plate

---

## Before coding

Figure out the measurements

- function bakeBread
  - Put 2 cups of flour in bowl
  - Put 1 cup water in bowl
  - Put 1 tsp yeast in bowl
  - Mix until 3 minutes has elapsed
  - Put in oven at 450 for 30 mins
  - Take bread out of oven
  - Cool on rack
  - return bread

- function sliceBread (bread)
  - Use knife to slice bread
    - : ERROR undefined slice
  - var sliceSize = 1/12;
  - Pick up knife
  - ERROR: Undefined cut through
  - Put knife on bread at sliceSize distance from end of bread
  - While a piece of bread has not fallen
    - Apply pressure to knife
    - Pull back and forth on the knife
  - return piece

- function spread(material, slice)
  - Take knife
  - Dip into material
  - Wipe on slice
  - return slice

- var loaf1 = bakeBread()
- var loaf2 = bakeBread()
- var slice1 = sliceBread(loaf1)
- var slice2 = sliceBread(loaf1);

- spread(jam, slice1)
- spread(peanutbutter, slice2)
