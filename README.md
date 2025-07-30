# EgoWalkTrajPred

Here is the GitHub repository for our paper, "Int2World: Egocentric Trajectory Prediction via Latent Intention-aware Interactive World Model" (Rongfeng Zhu, Bo Zhang, Anwar Saeed, Hongbo Liu and Ruili Wang):

Examples of the EgoWalk video data is available for download at [Link 1](https://drive.google.com/drive/folders/1jNs6y97eu1keCNyBiOCdzJE6CLLNLmzO?usp=sharing).

Examples of the EgoWalk dataset is available for download at [Link 2](https://drive.google.com/drive/folders/12QVoaiouw3NhAgmulVxmB-smt8ayXe4b?usp=sharing).

It will be fully released once the paper is published.

The data within the training and testing pickle files is structured as detailed below. These files contain 10566 training samples and 2634 test samples, respectively.

```
{sample_id: {'camera_wearer_traj': the trajectory of the camera wearer (stored in the TUM trajectory format. 10 time steps in total. 
                                   The first 3 time steps are for observation, and the remaining 7 are for prediction),
             'nearby_people': the trajectories of nearby people in the observation period, and they are stored in the following format:
                              {person_index: {'keypoints': the body keypoints of the tracked nearby person,
                                              'bbox': the bounding box of the tracked nearby person,
                                              'center': the center of the tracked nearby person},
                               ...
                              },                                                         
             'semantics_encoding': the Mean encoding of the scene semantics in the observation (3 time steps) and prediction (7) period 
                                   (10 semantic segmentation maps),
             'semantics_encoding_sigma': the Variance encoding of the scene semantics in the observation (3 time steps) and prediction (7) period 
                                   (10 semantic segmentation maps),
             'the_first_image_id': the image ID for the first timestep observation (e.g., 1-4-6601) consists of the image's storage location (1-4) and its sampling ID (6601). Images are sampled from the video at 2fps (e.g., frames 1, 16, ...).
            },
 ...
}
```

