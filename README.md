#Code and Data for CIKM'16 paper: Learning Points and Routes to Recommend Trajectories
---------------------------------------------------------------------------------------


##IPython notebooks
* `rank_markov.ipynb` IPython notebook to recommend trajectories using methods described in paper.
* `parse_results.ipynb` IPython notebook to generate performance tables (Table 3 and Table 4 in paper) using dumped results.


##Dataset
* `data/poi-Edin.csv` POI data in Edinburgh.
    * `poiID` POI identity
    * `poiCat` POI category
    * `poiLon` POI longitude
    * `poiLat` POI latitude
* `data/traj-Edin.csv` Trajectories in Edinburgh.
    * `userID` User identity
    * `trajID` Trajectory identity
    * `poiID` POI identity
    * `startTime` Timestamp that the user started to visit this POI
    * `endTime` Timestamp that the user left this POI
    * `#photo` Number of photos taken by the user at this POI
    * `trajLen` Number of POIs visited in this trajectory by the user
    * `poiDuration` The visit duration (seconds) at this POI by the user
* `data/poi-Glas.csv` POI data in Glasgow.
* `data/traj-Glas.csv` Trajectories in Glasgow.
* `data/poi-Melb.csv` POI data in Melbourne.
* `data/traj-Melb.csv` Trajectories in Melbourne.
* `data/poi-Osak.csv` POI data in Osaka.
* `data/traj-Osak.csv` Trajectories in Osaka.
* `data/poi-Toro.csv` POI data in Toronto.
* `data/traj-Toro.csv` Trajectories in Toronto.
* `data/rand-*.pkl` Dumped recommendations by method `Random` described in paper.
* `data/rank-*.pkl` Dumped recommendations by methods `PoiPopularity` and `PoiRank` described in paper.
* `data/tran-*.pkl` Dumped recommendations by methods `Markov` and `MarkovPath` described in paper.
* `data/comb-*.pkl` Dumped recommendations by methods `Rank+Markov` and `Rank+MarkovPath` described in paper.
* `data/ijcai-*.pkl` Dumped recommendations by method `PersTour` proposed in [this paper](http://dl.acm.org/citation.cfm?id=2832496) and its variant `PersTour-L`.


##Usage
To generate recommendations from scratch, please follow these four steps:

1. Install [rankSVM implementations](https://www.csie.ntu.edu.tw/~cjlin/libsvmtools/#large_scale_ranksvm) and assign the directory/path to variable `ranksvm_dir` in notebook `rank_markov.ipynb`.
1. Install Python modules imported in notebook `rank_markov.ipynb`.
1. Modify the value of dataset index variable `dat_ix` (feasible values: `0, 1, 2, 3, 4`) to run notebook `rank_markov.ipynb` on different dataset, results (.pkl file) will be saved in the directory specified by variable `data_dir`. 
1. After running notebook `rank_markov.ipynb` on all 5 datasets, please run notebook `parse_results.ipynb` to generate Table 3 and Table 4 in paper.


##Citation
Please cite these two papers if you use this dataset in your work.

* Kwan Hui Lim, Jeffrey Chan, Christopher Leckie and Shanika Karunasekera. "Personalized Tour Recommendation based on User Interests and Points of Interest Visit Durations". In Proceedings of the 24th International Joint Conference on Artificial Intelligence (IJCAI'15). 2015.
* Dawei Chen, Cheng Soon Ong and Lexing Xie. "Learning Points and Routes to Recommend Trajectories". In Proceedings of the 25th ACM International Conference on Information and Knowledge Management (CIKM'16). 2016.
