# Sentinel3_SNAPPY
Download Sentinel3 files and process via snappy

# 下载哨兵3LSTzip.ipynb
用于下载哨兵3 LST数据（zip格式）。使用ODATA API：https://documentation.dataspace.copernicus.eu/APIs/OData.html
需要设置账号密码

# SNAPPY_Sen3Preprocess.ipynb
使用Snappy库进行图像预处理。需要先在本地下载ESA SNAP。
包括了：
- Subset裁剪
- Reproject重投影：由于Sen3的数据用的是地理查找表，对应的控制点用于投影，所以如果只是丢进ArcGIS重投影或是用别的重投影会导致有shift偏移。
- 去云：使用波段运算apply掩膜。

# GoogleDriveDownload.ipynb
由于我是下载到了Google Drive，解压后发现有些zip文件损坏。因此这个代码用于检查本地文件zip和GoogleDrive中对应的文件是否大小一致，若不一致则重新从GoogleDrive中下载这个文件覆盖原有的损坏的文件。
