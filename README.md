# MOT with ByteTrack
## Introduction

This repo achieved highly efficient and accurate multi-target tracking through the selection of the tracker (ByteTrack) and in combination with the target detection model (YOLOv8)[YOLOv8](https://github.com/ultralytics)

<div align=center><img src="https://github.com/Kotka334/MOT/blob/86096a052f173d905650074c9184239d72234a40/out.gif"></div>

 ## Data Presentation

<div align="center">

<!-- START TRACKER TABLE -->
| Tracker | Status  | HOTA↑ | MOTA↑ | IDF1↑ |
| :-----: | :-----: | :---: | :---: | :---: |
| [botsort](https://arxiv.org/abs/2206.14651) | ✅ | 26.671 | 21.032 | 25.544 |
| [strongsort](https://arxiv.org/abs/2202.13514) | ✅ | 29.390 | 24.312 | 29.985 |
| [bytetrack](https://arxiv.org/abs/2110.06864) | ✅ | 34.866 | 29.548 | 39.848 |
| [ocsort](https://arxiv.org/abs/2203.14360) | ✅ | 33.637 | 26.088 | 37.409 |
| [imprassoc](https://openaccess.thecvf.com/content/CVPR2023W/E2EAD/papers/Stadler_An_Improved_Association_Pipeline_for_Multi-Person_Tracking_CVPRW_2023_paper.pdf) | ✅ | 29.173 | 29.656 | 30.089 |

<!-- END TRACKER TABLE -->

<sub> NOTES: The evaluation was conducted on the second half of the MOT17 training set, as the validation set is not publicly accessible. The pre-generated detections and embeddings used, were sourced from [here](https://drive.google.com/drive/folders/1zzzUROXYXt8NjxO1WUcwSzqD-nn7rPNr). Each tracker was configured with the original parameters provided in their official repositories. </sub>

</div>

</details>


## Installation

### First
Start with [**Python>=3.9**](https://www.python.org/) environment.

If you want to run the YOLOv8, YOLOv9 or YOLOv10 examples:

```
git clone https://github.com/mikel-brostrom/boxmot.git
cd boxmot
pip install poetry
poetry install --with yolo  # installed boxmot + yolo dependencies
poetry shell  # activates the newly created environment with the installed dependencies
```
### Then
Run the program
```
!poetry run python tracking/track.py --yolo-model <Your YOLO model path> --reid-model <Your REID model path> --source <Your video path> --save --conf <Confidence threshold> --tracking-method <Tracking method> --save-txt

```

## Bytetrack
[BYTETrack: Multi-Object Tracking by Associating Every Detection Box](https://arxiv.org/abs/2110.06864) is a paper presented at ECCV2022 by Yifu Zhang et al. Thanks to its universal framework and relative simplicity, it has been adopted by many subsequent researchers for their MOT trackers (Bot-SORT, SMILEtrack).

## Demo Link
![YouTube](https://youtu.be/XZ4otM8r0nM)
