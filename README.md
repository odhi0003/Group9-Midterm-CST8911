# Group 9 - Jane (Part 1): Blob Storage and Data Factory

## Completed

- Created Azure Blob Storage with a sales-data container
- Uploaded the sales CSV dataset.
- Created Azure Data Factory: group9-sales-df.
- Configured the CSV source and processed-data destination.
- Created and tested pipeline_salesdata successfully.
- Added basic failure handling using the CopyError variable.
- Exported the pipeline JSON and ARM template ZIP.

## Files

- sales_data_sample.csv: Original dataset.
- pipeline_salesdata.json: Pipeline definition.
- ARM template ZIP: Exported Data Factory configuration.

## Instructions for Member 2

1. Create a resource group `group9-midterm` - region(Canada Central).
2. Extract the ARM template ZIP folder.
3. Deploy the ARM template
   - In Azure Portal, search for **Deploy a custom template** or **Template deployment**.
   - Select **Build your own template in the editor** if prompted.
   - Open `ARMTemplateForFactory.json` in a text editor.
   - Copy all its contents into the Azure template editor.
   - Click Save.
   - Select the subscription and resource group
   - Review the parameters. Update the Data Factory name if necessary
   - Click Review + create → Create.

4. Check the Data Factory
   - Search for `Data factories` in Azure Portal.
   - Open the deployed Data Factory.
   - Click `Launch Studio`.
   - Under Author, check whether the pipeline, datasets, and linked services appear.

5. Create storage if it wasn't included
   - Search for Storage accounts → Create.
   - Use the same resource group and region.
   - Choose Standard performance and Locally-redundant storage (LRS).
   - Create a private container named **sales-data**.
   - Create another private container named **processed-data**.
   - Upload the sales csv file to sales-data.

6. Update the storage connection
   - In Data Factory Studio, open Manage → Linked services.
   - Open the blob storage.
   - Select the new storage account and configure authentication.
   - Click Test connection → Save.
   - Under Author → Datasets, verify that the source points to sales-data and the sink points to processed-data.

7. Test the setup
   - Open pipeline_salesdata.
   - Click Validate all.
   - Click Debug.
   - Confirm the pipeline succeeds.
   - Check processed-data for the copied CSV.

## Notes

I have added my screenshots for naming references if needed.