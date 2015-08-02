# Scouts on the ground

## Find gaps in sensors measurements

![Image of Mothership](https://github.com/Svetixbot/scouts-on-the-ground/blob/master/mothership.png)

Scouts are spread around a planet and receive all the data from sensors. This information is collected at every scout and get transdered every minute to mothership for futher processing. 

Sometimes sensors fail and stop collecting and sending information to the scouts. Although each sensor has fault tollerant capability to reset themselves in case of fail, there will be a gap in measurements sometimes. 


## Challenge: let's find data loss!

### Input format: 

| scout| port | sequence | time_interval                                       |
|----- |:----:| --------:| ---------------------------------------------------:|
| 24   | 1    | 23162    | "[""2015-07-20 10:15:31"",""2015-07-20 10:16:08"")" |
|24|1|23163|"[""2015-07-20 10:16:09"",""2015-07-20 10:17:08"")"|
|24|1|23164|"[""2015-07-20 10:18:31"",""2015-07-20 10:19:08"")"|
|24|2|23165|"[""2015-07-20 10:15:31"",""2015-07-20 10:16:08"")"|
|24|3|23166|"[""2015-07-20 10:15:31"",""2015-07-20 10:16:08"")"|
|6|1|40671|"[""2015-07-20 10:16:09"",""2015-07-20 10:16:46"")"|


### Output: 
| scout | port | loss_inteval |
|----- |:----:| --------:|
| 24 | 1 | "[""2015-07-20 10:17:09"",""2015-07-20 10:18:30"")"
