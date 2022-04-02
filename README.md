# WHEN AI LEARNS THE MUSIC
### _Powered by The Deep Sleeping Crew (Group6)_

<img src="https://miro.medium.com/max/810/1*kRRiGuDIoRF9OAKBRA6gmg.jpeg"> 

## Highlights
pending

## 1. Introduction
> Sounds are all around us, from birds chirping and waves lapping against a coastline to cars honking in traffic. But sometimes sounds are put together in purposeful ways to create a specific atmosphere or to express ideas or emotions. Such organized sounds are called **`"music"`**.
Song is a collection of coordinated sounds which have a lot of elements including quantity in terms of engineering, art mixture, even its maker such as artist, composer both can effect to many version of the song.

However, the indicator which is the best representative for identification is the **`"song name"`**. Even if that song may be sung by a new artist under different conditions. A human can sense and separate the song's identity and communicate via song name

The one of big pain points we commonly face is hearing just only one part of the song and falling in love with it but don't know its name

Our team would like to solve this problem with AI by applying **`Sequential models`** such as **`RNN`**, **`LSTM`**, and **`GRU`** for **`multi-classification`**

Input: Feature of the song (**`Amplitude`** and **`Frequency Domain`**)

Output: **`Song Name`**

## 2. Dataset

### Data source
mp3 file downloaded from YouTube with 2 versions, the **`original`** and **`cover`** version. We use the song covered by another artist to be the **`test dataset`**

### Data pre-processing
From our research, there are 2 ways for collecting the song.

1. **`Amplitude`** - convert the **`song file`** to the Amplitude wave which has the **`sr(sampling rate) = 100/second`**. We set up the model to **`hear the song for 5 seconds and predict the song name`**. So 1 row of data has 500 features of amplitude at the time. Then the data has been stored in a **`csv file format`** and **`labeled with the song name`** to train the model further.
2. **`Frequency domain`** - convert amplitude wave to domain frequency with technique **`Mel Frequency Cepstral Co-efficients`** which built in package **`librosa`**. In this study, we separate **`13 frequency sub-group`**. Then the data has been stored in a **`csv file format`** and **`labeled with the song name`** to train the model further.

## 3. Network Architecture
**`RNN`**

<img src="image/RNN arche.png"> 

**`LSTM`**

<img src="image/LSTM arche.png"> 

**`GRU`**

<img src="image/GRU arche.png"> 

## 4. Training

Train: 80% validation: 20%

Epoch: 100

Batch size:  100

Loss: sparse_categorical_crossentropy

Optimizer: Adam

## 5. Result
**`Amplitude`** Input
| Model | Train Accuracy  | Test Accuracy |
| ------ | :------: | :------: |
| 1. RNN | 16.00% | 11.11% |
| 2. LSTM | 25.90% | 9.36% |
| 3. GRU | 19.00% | 8.49% |

**` Frequency domain`** Input
| Model | Train Accuracy  | Test Accuracy |
| ------ | :------: | :------: |
| 1. RNN | 93.37% | 42.86% |
| 2. LSTM | 90.36% | 71.43% |
| 3. GRU | 96.39% | 71.43% |

## 6. Discussion

•  The result from amplitude datasets couldn't make good progression. After the change of preprocessing method from amplitude to the frequency domain, the accuracy surprisingly improve. This indicates that domain expertise is very important in training machine learning since the team doesn’t have fundamental knowledge about sound.

•  RNN model has less accuracy compared to LSTM and GRU which is obvious because of fewer parameters than the other two. LSTM and GRU is nearly equal in term of accuracy. But 3 of them have less test accuracy compared to train accuracy which means overfit.

•  The training dataset which collects 2 versions for each music is still low. To make the model more robust for various kinds of input, more versions of music should be collected.

## 7. Conclusion

LSTM and GRU are outperformed RNN in both amplitude and frequency domains. Although the outstanding performance, all three models still need more data to train to make the model more robust due to the overfitting problem.

## End Credit
 This study is a part of **`Deep Learning course`**  (BADS7604), Businuss Analytics and Data Science, National Institute of Development Admistration (**`NIDA`**)

### _The Deep Sleeping Crew (Group6) Contribution - Uniform_
**`16.67%`** 🍕 - **`6310422057`** Natdanai Thedwichienchai 

**`16.67%`** 🍕 - **`6310422061`** Wuthipoom Kunaborimas 

**`16.67%`** 🍕 - **`6310422063`** Nuj Lael 

**`16.67%`** 🍕 - **`6310422064`** Krisna Pintong

**`16.67%`** 🍕 - **`6310422065`** Songpol Bunyang

**`16.67%`** 🍕 - **`6310422069`** Phawit Boonrat
