# Polar Scatter Plot in MATLAB

This repository contains a MATLAB project to create **polar scatter plots** using data from an Excel file. The plot visualizes points in polar coordinates (angle and radius) with color coding based on a third variable.

## Features

- Reads data from an Excel file (`polar_plot.xlsx`)
- Plots a polar scatter plot using `polarscatter`
- Colors points based on a third column of data
- Customizable radius and angle limits
- Custom colormap and alpha transparency
- Month names as angular labels

## Files

- `polar_scatter_plot.m` : MATLAB script to generate the polar scatter plot  
- `polar_plot.xlsx` : Sample data (columns: angle in degrees, radius, color value)  
- `README.md` : Project description

## How to Use

1. Clone or download this repository.
2. Open MATLAB and navigate to the project folder.
3. Make sure `polar_plot.xlsx` is in the same folder as the script.
4. Run the script `polar_scatter_plot.m`.
5. The polar scatter plot will be displayed with color-coded points and month labels.

## Requirements

- MATLAB (R2016b or later recommended)
- Excel file with at least three columns: angle (degrees), radius, and color value

## Example

```matlab
clc;
clear;
close all;

file_path = 'polar_plot.xlsx';
data = xlsread(file_path);

th = deg2rad(data(:,1));
r  = data(:,2);
c  = data(:,3);

polarscatter(th,r,50,c,'filled','MarkerFaceAlpha',0.95)
rlim([0.89 1])
thetalim([90 180])
colormap jet
colorbar
thetaticks(0:30:330)
thetaticklabels({'Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct
