# Java-assignment
You are given an integer array height of length n. There are n vertical lines drawn such that the two endpoints of the ith line are (i, 0) and (i, height[i]).  Find two lines that together with the x-axis form a container, such that the container contains the most water. Return the maximum amount of water a container can store. 


Explain the code in slow & detail
    public int MaxArea(int[] height) {
        int left = 0;
        int right = height.Length - 1;
        int maxArea = 0;
        
        while (left < right)
        {
            int area = (right - left) * Math.Min(height[left], height[right]);
            if (area > maxArea) maxArea = area;
            
            if (height[left] > height[right]) right--;
            else left++;
        }
        return maxArea;
    }
