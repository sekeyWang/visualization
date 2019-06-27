# 数据可视化

问题描述：https://www.kaggle.com/c/siim-acr-pneumothorax-segmentation/overview

根据 https://www.kaggle.com/akashdeepjassal/data-visualization 对sample数据进行数据可视化的过程

sample数据中包括5个气胸数据和5个非气胸数据，数据的标签在train-rle-sample.csv中，第一列为image的名字，第二列为image的标签。

标签为-1表示该图为不包含气胸，如果不为-1，该数据为rle(run-length-encoded)编码后的气胸位置，编码规则如下：

以数据 810584 20 1003 22 1001 25 998 28为例，气胸的位置在(810584, 810584+20), (810584+20+1003, 810584+20+1003+22)...

通过运行test.py，可以显示图像，气胸位置，病人属性等

show_dicom_info函数用于显示该图像的所有属性，show_dic_info用于病人的重要属性，包括病人id，性别，年龄等

通过show_image函数可以查看图像：如果标签为-1，则通过plot_pixel_array直接显示图像，
如果标签不为-1，则会通过plot_with_mask_and_bbox函数将含有气胸图片的气胸位置标注在图片上
