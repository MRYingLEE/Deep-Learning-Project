# MsAIProject
This is a solution to a public competition, DAT264x: Identifying Appliances from Energy Use Patterns ( https://www.datasciencecapstone.org/competitions/10/appliances-energy-use/). The required accuracy is 85%. My accuracy is only 93%, not in the top list.  But I used a simple and maybe robust way. I wish someone may find this useful as an AI practice.

## The backgroud
This project is the final step to get Microsoft Professional Program Certificate in Artificial Intelligence. This project uses a real world dataset. You may find the detail at https://www.datasciencecapstone.org/competitions/10/appliances-energy-use/page/31/. 

In short, "In this challenge, you will use standard AI tools to identify 11 different types of appliances from their electric signatures, quantified by current and voltage measurements".

## My different ideas

For all data are in spectrogram images, it's natual to use CNN (Convolutional neural network）. But the real meaningful part of chart is stable. I think to use average spectrum array to simplify the problem is a good idea. Then I used multi layer logistic regression model.

By my method, the data size for each sample is shrinked from 118x128x2 to 128x2. So that the speed can be much faster.

## Steps
1. To convert each sample (both current and voltage) in spectrogram (118X128)x2 to array (128x2). In this step, only the right part of the spectrograms are used to reduce the noise in the left part.
2. To save simplified data sample (128x2) along with the lable into CNTK text file. (train.txt and test.txt in folder PLAID).
3. To use multi layer logistic regression to train the model and test.
4. To adjust super parameters to get a better results. 

## References on spectrogram
python - How extract numpy array features from spectrogram? - Stack Overflow (https://stackoverflow.com/questions/45708460/how-extract-numpy-array-features-from-spectrogram)

image - python -- measuring pixel brightness - Stack Overflow (https://stackoverflow.com/questions/6442118/python-measuring-pixel-brightness)

python - how to reverse color map image to scalar values - Stack Overflow (https://stackoverflow.com/questions/3720840/how-to-reverse-color-map-image-to-scalar-values)






