# Lane Detection
It's 4 AM and i'm tired af but I don't wanna forget what I learned in the last 5 hours. 

Lane detection is done initally using an image that you gray scale and gaussian blur. The blur helps the next part which is to take the derivative at each pixel in both x and y directions (so the gradient) in order to find where the largest differences are. This is known as canny edge detection. After that, you create a polygon mask to mask all the areas in the image where you don't want the edges of... this is honestly a lot harder than it seems when it comes to shitty video. Past that, the points captured by the edge detection are brought through a Hough transform where points become families of lines. When all the points are plotted, it is easy to then see that there is an intersection between all the points in the H transform. That point is gives us the slope and y intercept of the line of best fit. At that point, lines with similar slopes are averaged togetehr to give us our left and right lane lines. They're then overlayed on the original image and voila... lane detection. 

Oh, also you just do this to every single frame so make sure you have A1 video lmao.


