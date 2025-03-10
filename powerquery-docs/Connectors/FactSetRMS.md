---
title: Power Query FactSet RMS connector
description: Provides basic information and prerequisites for the FactSet RMS connector, and includes descriptions of the optional input parameters.
author: bezhan-msft
ms.service: powerquery
ms.topic: conceptual
ms.date: 04/03/2022
ms.author: bezhan
LocalizationGroup: reference
---

# FactSet RMS (Beta)

## Summary

| Item | Description |
| ------- | ------------|
|Release state | Beta |
| Products supported | Power BI (Datasets) |
| Authentication types supported| Basic |
| Function reference docs | https://developer.factset.com/api-catalog/irn-notes-api|

> [!NOTE]
> The following connector article is provided by FactSet, the owner of this connector and a member of the Microsoft Power Query Connector Certification Program. If you have questions regarding the content of this article or have changes you would like to see made to this article, visit the FactSet website and use the support channels there.

## Prerequisites

To start using the FactSet RMS connector, the following prerequisite steps need to be completed.

* Download Power BI

  * Ensure that you're using latest version of Power BI, as the latest major update to the FactSet Power BI data connector will only be available there. Any subsequent major or minor version updates will only be available by upgrading Power BI.

* Subscription and authentication

  * To access FactSet’s IRN, the appropriate subscription is required. Refer to the FactSet Client Assistance page for more details.

  * With the subscription in place, the next step is to generate the API key from the Developer Portal. Follow the steps outlined in [FactSet API keys Authentication v1 documentation](https://developer.factset.com/authentication).

## Capabilities supported

* Import

## Connect to FactSet RMS from Power Query Desktop

To import data using the FactSet RMS connector from Power Query Desktop, take the following steps:

1. Open Power BI Desktop.

2. On the Power BI Desktop home page, select **Get Data** > **More**.

    [![Image of Get Data drop down box with the More option emphasized.](./media/factset-rms/OpenPowerBi.png)](./media/factset-rms/OpenPowerBi.png#lightbox)

3. To connect to FactsSetRMS, search for **FactSet** in **Get Data** and select the FactSet RMS connector from the right-hand list.

   ![Image of the Get Data dialog box with FactSet RMS (Beta) emphasized.](./media/factset-rms/SelectFactSetRMS.png)

4. In the authentication page, you'll be prompted to enter the Username - Serial and the API key. Go to the FactSet Developer Portal for more instructions on setting up an API Key.

   ![Image of the Authentication dialog box with a username and API key entered.](./media/factset-rms/Authentication.png)

5. The connector opens the Power Query navigator with a list of all provided functions. Note that all functions might not be available, depending on your available subscriptions. Your account team can assist with requirements for access to additional products.

   [![Image of the Navigator dialog box with a list of all of the provided functions.](./media/factset-rms/Navigator.png)](./media/factset-rms/Navigator.png#lightbox)

6. Use the Get\* queries to look up parameters for your Notes and create new queries. A form will populate in the query window with parameter fields to narrow your universe and return the relevant data set of interest based on IRN Subject, Author, Date Range, Recommendations and/or Sentiments. Note that the functions contain Get\* queries that are common for IRN Notes, Custom Symbols, and Meetings APIs.

   [![Image of the parameters that are available to the GetNotes function.](./media/factset-rms/Queries.png)](./media/factset-rms/Queries.png#lightbox)

   The following table describes the Get functions in the connector.

   | Function Name | Function Description |
   | --------------- | ----------- |
   | GetNotes | Gets all the notes, including non-extended text custom fields in the specified date (startDate and endDate) range, and can be filtered on subjectId, authorId, recommendationId, sentimentId, and modifiedSince. |
   | GetNote | Gets details of a note, including note body and extended text custom fields. |
   | GetMeetings | Gets all the meetings, including non-extended text custom fields in the specified date (startDate and endDate) range, and can be filtered on modifiedSince. |
   | GetMeeting | Gets details of a meeting, including meeting body and extended text custom fields. |
   | GetCustomSymbols | Gets a list of all custom symbols in your IRN database, along with standard field data and non-extended text custom fields data, and can be filtered on CustomSymbolTypeName. |
   | GetCustomSymbol | Gets details of a custom symbol, including symbol description and extended text custom fields.|

7. Results will be returned as a table with notes and a custom field.

   [![Image that shows the data that was returned as a table.](./media/factset-rms/Result.png)](./media/factset-rms/Result.png#lightbox)