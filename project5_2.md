### Project 5, Part 2

#### question 1

#### question 2


knn range (10, 80) max test score at 73, 0.5583211322596389 1
knn range (70, 80) max test score at 77, 0.550024402147389 img 2

knn range (70, 80) 73, 0.5026842362127867 with weight img 3

log reg 0.5481770833333334, 0.5510004880429478; 0.5380859375, 0.5588091752074182 (train, test scores)

random forest: though all were close, n=1000 consistently performed best

min num splits for random forest: 28 or 29
28 0.5446559297218155
29 0.5436798438262567 most training scores were .65 ish
img 4: table of scaled data when performing rfc, n=100
5: table of training and testing scores for rfc for (100, 500, 1000, 5000)  compare to 6, 7 (scaled)

2&3 combined
8:knn range (10, 80) max test score 72, 0.5607613469985359
9: knn range (60, 80) max test score 71, 0.5578330893118595
10: knn with weight range (10, 80) 67, 0.5231820400195217
0.5485026041666666, 0.5490483162518301; 0.5465494791666666, 0.5539287457296243 log regression

11: rfc all were close n=5000 consistently performed better
min num splits for random forest 29 or 28
29 0.5436798438262567
28 0.541727672035139
12, 13: scaled rfc with 100, 500, 1000, 5000 compare with 11??

