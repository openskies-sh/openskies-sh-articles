---
title: "Aerobridge.io: How to add a new component to Assembly?"
date: 2022-10-31
draft: False
categories: ["aerobridge","documentation"]
tags: ["aerobridge-howto"]
---

In this article you will learn how to acknowledge custody of a new part and replace the part on a drone and the associate that replacement on Aerobridge Management Server. To perform these actions, you will need a account in Aerobridge, to get a account for yourself, please join us during our [office hours](https://outlook.office365.com/owa/calendar/AerobridgePro@openskies.sh/bookings/).
<!--more-->

### Prerequisite
A incident must be recorded prior to starting this article, to see how to report an incident and associate a component with that Incident Report, please see the [help article]({{< ref "aerobridge-report-incident.md" >}} "Report an Incident"))

### The background and actions
Once an incident has been reported, normally staff within your operation will inspect the impacted component and based on the inspection, can order a new part or fix the damaged one. In this case we assume the impacted component is damaged beyond repairs and that a new part is ordered and replaced. 

### Applies to 
**Aerobridge Lite Plan** and above

### What you need? 
For this step, you will need:

- an account with the Lite plan in Aerobridge with your fleet details
- an incident report created with the impacted component
- a photo / image of the receipt from the purchase

### Report an incident
Follow the following steps update the component assembly. This is essentially a three-step process where you upload the photo of the receipt first, then you acknowledge custody of the new component ad finally after replacing the part on the drone, you update the component assembly. : 

1. Step 1. Upload your photo
    - Go to ```Data locker -> Files Manager```
    - Click on ```+ Add a file```
    - Upload tour photo and select ```File type``` as ```Receipts``` or ```Invoices``` in the dropdown
2. Step 2. Acknowledge custody
    - Go to ```Manufacturing -> Assemblies```
    - Select the impacted aircraft assembly, normally this should have a "*Parts need review*" status
    - Your component family should be avaialble on the left, click on the ```+ Acknowledge custody of new one``` button 
    - Select the appropriate Invoice Receipt and give it a Assembly code, a friendly name
3. Step 3. Update Assembly
    - Assuming that you have replaced the part on the vehicle, it is now time to update the assembly on the management server
    - Go to ```Manufacturing -> Assemblies```
    - Select the impacted aircraft assembly, normally this should have a "*Parts need review*" status
    - On the right hand side, you should see the missing compoents and additionally it should show the "number of comonents available" to be added to the assembly. 
    - Click on "Add to Assembly" to be added to the assembly

The assembly status should now be complete

### Video Demonstration
{{< youtube ZPjMuc1Xmuo >}}
