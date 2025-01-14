# Update Retention Labels on SharePoint Document Library

This PowerShell script uses the Microsoft Graph PowerShell SDK to update retention labels on a SharePoint document library. The script connects to Microsoft Graph, retrieves the specified document library, and updates the retention labels as needed.

## Prerequisites

- PowerShell 7.0 or later
- Microsoft Graph PowerShell SDK
- Appropriate permissions to access and modify the SharePoint document library (script uses delegated permissions)

## Permissions

The following permissions are required to run this script:

- **Files.ReadWrite.All**: Allows the app to read and write to all files.
- **Sites.ReadWrite.All**: Allows the app to read and write to all site collections, including overriding record labels.
- **RecordsManagement.Read.All**: Allows the app to read retention labels configured in Purview.

## Installation

1. Install the Microsoft Graph PowerShell SDK if you haven't already:

    ```powershell
    Install-Module Microsoft.Graph -Scope CurrentUser
    ```

2. Clone this repository or download the script file.

## Usage

1. Open PowerShell and navigate to the directory containing the script.

2. Run the script with the required parameters:

    ```powershell
    .\Update-RetentionLabelsOnSPOFiles.ps1 -SiteUrl "https://yourtenant.sharepoint.com/sites/yoursite" -DocumentLibraryName "Documents" -OldRetentionLabelName "YourOldRetentionLabel" -NewRetentionLabelName "YourNewRetentionLabel"
    ```

### Parameters

- `-SiteUrl`: The URL of the SharePoint site containing the document library.
- `-DocumentLibraryName`: The name of the document library to update.
- `-OldRetentionLabel`: The retention label to update from on the documents in the library.
- `-NewRetentionLabel`: The retention label to update to on the documents in the library.

## Example

```powershell
.\Update-RetentionLabelsOnSPOFiles.ps1 -SiteUrl "https://yourtenant.sharepoint.com/sites/yoursite" -DocumentLibraryName "Documents" -OldRetentionLabelName "YourOldRetentionLabel" -NewRetentionLabelName "YourNewRetentionLabel"
