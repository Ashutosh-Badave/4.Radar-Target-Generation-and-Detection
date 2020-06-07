# 2D CFAR Implementation

## 1. Implementation steps for 2D CFAR
> 1. Grid window is calculated based on gaurd cells and training cells. To run over 2D array, 2 loops are used to 1 to run over row and inside of that another loop for colomns.
> 2. Inside rows loop, col loop is called, in which firstly total noise in that grid window is calculated considering training + guard + CUT cells.
> 3. Then noise value in gaurd and CUT cells is calculated.
>4. with help of this, training cells noise levels are calculated by subtracting gaurd +CUT noise from total noise. 
>5. Offset is added in that noise level to find the threshold value.


## 2. Selection of training , Gaurd cells and offset

> Firstly I have assumed all the values based on logical maths that the no of training cells should be twice than the gaurd cells.
> Then done trial and errors for every value to find the best suitable option for this model.
> simillarly first value for offset is assumed as 4 for calculation purpose then it is increased after checking the training cell noise levels for few values. 

## 3. Steps taken to suppress the non-thresholded cells at the edges
> After doing CFAR thresholding, I got 2D array of size(498*122) something, to keep the map size same , I have used padding of zeros at the edges on the both side of 2D CFAR array using padarray function. 
> Padding is giving the issue in getting the correct output, so I removed that part and created the Signal_CFAR with zeros of required size. 
