Experiment files:
- alt.csv corresponds to the figure titled "Alternating traffic";
- uni.csv corresponds to the figure titled "Unidirectional traffic";
- def-uni.csv corresponds to the figure titled "Deferred unidirectional traffic".

Instructions for running the experiments:
- Download and checkout the branch 'journal' [here](https://github.com/qantik/ratcheted/tree/journal) and follow the instructions to install dependencies (commit digest de659d80a9ecdf353a2acd44e2efea3196851364). You can do this by running:

```
git clone -b journal github.com/qantik/ratcheted
```
- The README file contains the following: "The bench directory within each package [i.e. the packages acd, dv, jmm, js and pr] contains the runtime, message and state size benchmarks which can be run by simply executing the main.go file". We will need to edit some of the main.go files a bit to run all experiments.
- Vary the second argument of ```time(arcad, time_alt)``` with ```time_uni``` and ```time_def``` to run all three types of experiments for a given scheme (in this case arcad). ```time``` may appear as ```size``` in a ```main.go``` file, which can be changed; ```size``` obtains benchmarking information corresponding to variable sizes.
- The first argument can be varied as follows:
	- ```arcad = dv.NewARCAD(..)``` corresponds to ARCAD-DV;
	- ```lite = dv.NewLiteARCAD(..)``` corresponds to liteARCAD;
	- ```sarcad = dv.NewSARCAD(gcm, aes, isOTEAE)``` corresponds to EtH when ```isOTEAE``` is ```false``` and EtUK when ```isOTEAE``` is true.
- The remaining benchmarks can be performed in:
	- /acd/bench for ACD and ACD-PK (using variable ```dr``` for ACD and ```drpk``` for drpk);
	- /jmm/bench for JMM;
	- /js/bench for JS;
	- /pr/bench for PR.
