# LS_NRA: Efficient Local Search for Nonlinear Real Arithmetic (VMCAI' 2024)

## Resources
paper link: https://link.springer.com/chapter/10.1007/978-3-031-50524-9_15

arxiv link: https://arxiv.org/abs/2311.14249

video: https://www.youtube.com/watch?v=CKGDRTXvKjk

slides: https://yogurt-shadow.github.io/assets/files/LS_NRA_slides.pdf

You can also visit the homepage of Zhonghan Wang, the first author of the work (https://yogurt-shadow.github.io/) to find something interesting.

## Code Structure

The main part of local search algorithm is based on original nlsat framework 
of z3 (`src/nlsat`). 
1. `nlsat_local_search.cpp` and `nlsat_local_search.h`: represents basic apis and algorithms.
2. `nlsat_advanced_types.h`: advanced structures of clauses and atoms, like storing arithmetic variables in them
3. `nlsat_solver.cpp`: this is the main part of original nlsat algorithm of z3, and also the entrance of our local search algorithm. Variable substitution and some simple equality constraints simplification are implemented here.
4. There are also some changes to make local search algorithms run normally. For example, `nlsat_evaluator.cpp` and `nlsat_evaluator.h` have been changed a little to calculate the infeasible set of an atom considering a specific variable (originally it can only support the maximum variable, which is the last variable to be assigned in a static variable order)

## Run
The running method is the same with Z3.

```bash
python scripts/mk_make.py
cd build
make -j20
```
Here replace `make -j20` by the threads available on your device.

To try to test a smt2 format file, run the following
```bash
cd build
./z3 <example.smt2>
```

## Contact
Zhonghan Wang, master student currently in Institute of Software, Chinese Academy of Sciences

wangzh@ios.ac.cn

wangzhonghan272@gmail.com