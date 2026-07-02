# dublin-core-bulk-metadata-from-image-to-csv-for-omeka-script
A Python Script that extracts Dublin Core metadata from digital images such as date, format, coverage and creates CSV for bulk upload of metadata into Omeka 

Generates a BatchUpload-compatible CSV for Omeka Classic from image files.

Workflow:
  1. Run this script from (or point it at) the folder containing your images.
  2. Choose an output filename and select which Dublin Core fields to bulk-set.
  3. Open the resulting CSV and fill in per-image values before uploading.
  4. In Omeka BatchUpload, upload the CSV and image files together.

Column mapping:
  - 'file'              → File (sidecar filename matched against uploaded file)
  - 'Dublin Core:Title' → DC Title element (explicit prefix avoids Omeka's
                          internal item-title field conflict)
  - All other headers are Dublin Core element names and auto-map by exact name.

Requires: exiftool  (sudo apt install libimage-exiftool-perl)

