---
title: CareerTeachers ARCRM
sidebar: cyclr_sidebar
permalink: careerteachers-arcrm-connector
tags: [connector]
---

# Running Custom Queries

Follow the steps below to set up to add a custom object to a connector.

The screenshots below document the process to recreate the following Nationalities query:

```json
{
  nationalities(orderBy: nationalityID_ASC){
    nationality{
      nationalityId
      nationality
    }
  }
}
```

1. Begin by editing the Access CRM connector. Copy the Custom queries category, providing the
   GraphQL query name as the object name. This will create a new instance of the custom queries
   category with the name you provided:
   ![Create Custom Object Category Instructions](./images/CareerTeachers-ARCRM1.png)
2. In the copied category, populate the Response Fields on the Run Custom Query method: ![Run Custom Query](./images/CareerTeachers-ARCRM2.png)
3. Supply the Query Arguments and your chosen Response Fields in the boxes provided:
   ![Supply Query Arguments](./images/CareerTeachers-ARCRM3.png)
   The custom method can now be executed as normal and will map as expected from within a Cycle.
   ![Custom Object Query Results](./images/CareerTeachers-ARCRM4.png)

   In order to implement the bespoke query below, the Query Arguments and Response Fields should be
   set to the following:

   ```json
   {
     bespoke_PlacementExtraDetailsSelect (placementID: 300997){
        bespoke_PlacementExtraDetailsSelectResults {
          placementId
          clientID
          startCheckOK
          jobID
        }
     }
   }
   ```

   Query Arguments: `placementID: 300997`

   Response Fields: `bespoke_PlacementExtraDetailsSelectResults {placementId, clientID, startCheckOK, jobID}`
