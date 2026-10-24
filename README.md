# Multi-Sport Polygon Segmentation Dataset

A sample dataset demonstrating polygon-based player segmentation across football, hockey, tennis, cricket and basketball images.

This project showcases how polygon annotations can outline player shapes in sports imagery for computer vision and AI model training.

## Project Overview

**Project Name:** Multi-Sport Polygon Segmentation Dataset  
**Annotation Type:** Polygon Segmentation  
**Annotation Class:** `Player`  
**Annotation Format:** COCO Instance Segmentation JSON  
**Annotation Tool:** CVAT  
**Organization:** Annomax AI

## Sports Covered

- Football
- Hockey
- Tennis
- Cricket
- Basketball

## Annotation Objective

The goal of this project is to demonstrate accurate player segmentation across different sports environments. Each labeled player is outlined with a polygon that follows the visible shape of the player's body as closely as possible.

The dataset demonstrates polygon annotation practices for sports imagery with different backgrounds, player poses, uniforms and viewing angles.

## Annotation Guidelines

Follow these guidelines when creating or reviewing annotations:

1. **Outline each player:** Draw a polygon around the visible player rather than using a rectangular bounding box.
2. **Follow object boundaries:** Place polygon points along the player's visible silhouette.
3. **Maintain tight boundaries:** Avoid including unnecessary background areas.
4. **Handle occlusion carefully:** Annotate the visible parts of a partially occluded player according to the project requirements.
5. **Separate individual players:** Create a separate polygon annotation for each visible player.
6. **Check polygon quality:** Avoid unnecessary points, self-intersections and gaps along the intended outline.
7. **Use the correct class:** Assign the `Player` category to each player annotation.
8. **Review before export:** Confirm that the polygons align with the players and the exported JSON references the correct images.

## Annotation Structure

The reference JSON follows the COCO instance segmentation structure.

| Field | Description |
|---|---|
| `images` | Image IDs, filenames and image dimensions |
| `categories` | Defines the annotation class |
| `annotations` | Contains individual player annotations |
| `segmentation` | Polygon coordinates outlining each player |
| `bbox` | Bounding box derived from the annotated object |
| `area` | Annotated segmentation area |
| `iscrowd` | Crowd annotation indicator |
| `attributes.occluded` | Indicates whether the player is occluded |

### Example JSON

The following is a simplified example of one player annotation. The coordinates are illustrative and are not copied from the actual dataset.

```json
{
  "id": 1,
  "image_id": 1,
  "category_id": 1,
  "segmentation": [
    [
      120.0, 80.0,
      145.0, 82.0,
      150.0, 130.0,
      135.0, 175.0,
      110.0, 170.0,
      105.0, 120.0
    ]
  ],
  "area": 3000.0,
  "bbox": [105.0, 80.0, 45.0, 95.0],
  "iscrowd": 0,
  "attributes": {
    "occluded": false
  }
}
```

The `segmentation` field stores polygon coordinates as alternating x and y values. The `bbox` field uses the COCO format `[x, y, width, height]`.

## Dataset Contents

```text
multi-sport-polygon-segmentation/
├── images/
│   ├── football/
│   ├── hockey/
│   ├── tennis/
│   ├── cricket/
│   └── basketball/
├── annotations/
│   └── instances_Train.json
└── README.md
```

This structure is a suggested organization for the repository. Adjust the folders and JSON filename to match the files you upload.

## Quality Assurance

The sample demonstrates the following quality checks:

- Polygon boundaries follow player silhouettes.
- Each annotation references a valid image and category.
- Polygon coordinates remain within image dimensions.
- Bounding boxes and segmentation areas are consistent with the polygons.
- Occlusion attributes are reviewed where applicable.
- The exported JSON is valid and follows the expected schema.

## Potential Applications

Polygon-based player segmentation can support research and development in:

- Sports video analytics
- Player detection and segmentation
- Sports scene understanding
- Player movement analysis
- Computer vision model development
- Automated sports analysis systems

This repository is a demonstration of annotation capabilities. It is not intended to represent a benchmark dataset or a validated training dataset unless further testing and documentation establish that status.

## About Annomax AI

Annomax AI provides AI data annotation and quality assurance services to support computer vision and machine learning projects.

Our work focuses on structured annotation, consistent labeling practices and quality-controlled datasets for AI development.

**Need polygon annotation or dataset QA support?**

Contact: `sales@annomaxai.com`

---

*Note: This is a sample dataset for demonstration purposes. Please verify the image usage rights and licensing before redistributing the images or using them commercially.*
