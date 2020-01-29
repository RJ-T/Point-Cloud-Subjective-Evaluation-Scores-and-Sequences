# Point-Cloud-Subjective-Evaluation-Scores-and-Sequences

This mat document is the MOS of our point cloud subjective evaluation. It is a 42*9 matrix. Each column of the matrix represents a point cloud sequence(from 1-9: redandblack, ULB_Unicorn, loot, longdress, romanoillamp, soldier, Staue_Klimt, Shiva and ulli wegner). Each raw of the matrix represents a certain kind of distortion and its distortion degree. The detailed information is as below:

1:6: OT, octree compression. The original point clouds are compressed by the popular octree pruning method provided in Point Cloud Library (PCL). Octree pruning is selected to present the artifacts after regular removal of points, in which a set of adjacent points are displaced by a single root node point. Under this type of compression, the contents are enclosed in an octree structure. Modifying the parameter in PCL named tree resolution, the resolution of the samples are adjusted correspondingly. By increasing the tree resolution, the number of points of the compressed object decreases. The percentage of removed points is: 15%, 30%, 45%, 60%, 75%, 90%, allowing the deviation of +-2%.

7:12: CN, color noise. 10%, 30%, 40%, 50%, 60%, 70% points are chosen to distort in RGB value (unit8 form), and the range of RGB change is +-10, +-30, +-40, +-50, +-60, +-70. If the processed RGB value is out of the range 0-255, it will be moved into the right range by adding or subtracting 256.

13:18: DS, random downsample. Random downsample the point clouds by removing 15%, 30%, 45%, 60%, 75%, 90% of the points in the original point clouds.

19:24: GN, gaussian noise. Add gaussian noise to the point clouds. All the points in the point cloud will be added a geometric shift that is 0.05%, 0.1%, 0.02%, 0.5%, 0.7%, 1.2% of the bounding box.

25:30: DC, the combination of DS and CN. The downsampling process is firstly applied and then the color noise is added. Naturally, the distortion parameters in 6 degrees changes correspondingly to the DS and CN parameters.

31:36: DG, the combination of DS and GN. The downsampling process is firstly applied and then the gaussian noise is added. The distortion parameters in 6 degrees changes correspondingly to the DS and GN parameters.

37:42: GC, the combination of GN and CN. The distortion parameters changes correspondingly to the GN and CN parameters.

The used orignial plys can be downloaded at: https://jbox.sjtu.edu.cn/l/onFb6F

The processed plys (with distortion) can be downloaded at: 
