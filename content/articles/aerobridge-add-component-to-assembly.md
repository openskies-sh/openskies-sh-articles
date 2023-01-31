---
title: "Aerobridge.io: How to add a new component to an Assembly?"
date: 2022-10-31
draft: False
categories: ["aerobridge","documentation"]
tags: ["aerobridge-howto"]
---

In this article you will learn how to acknowledge custody of a new component via Aerobridge Management Server. Once custody is acknowledged and installed / replaced on the drone, the component must be associated to an assembly on the [Aerobridge](https://aerobridge.io). To perform these actions, you will need a account in Aerobridge, to get a account for yourself, please join us during our [office hours](https://outlook.office365.com/owa/calendar/AerobridgePro@openskies.sh/bookings/).
<!--more-->

### Prerequisites
An event must be recorded prior to starting this article, once a event is reported against a component, depending on the status the component is removed from the assembly automatically. To see how to report an event and associate a component with that Event Report, please see the [How to report an event?]({{< ref "aerobridge-report-events.md" >}} "Reporting Events")) article.

### The background 
Once an event has been reported, and the associated component isset as damaged, the component assembly is marked as ```parts need review```. Normally staff within your company will inspect the impacted component and based on the inspection, they can order a new part or fix the damaged one. In this case we assume the impacted component is damaged beyond repairs and that a new part is ordered and replaced. 

### Applies to 
**Aerobridge Lite Plan** and above

### What you need? 
For this step, you will need:

- an account with the Lite plan in Aerobridge with your fleet details
- an {{< relref "aerobridge-report-events.md" >}} event report created with the impacted component 
- a photo / image of the receipt from the purchase of the replacement component

### Update component assembly
Follow the following steps update the component assembly. This is essentially a two-step process where you upload the receipt first, then you acknowledge custody of the new component ad finally after replacing the part on the drone, you update the component assembly. 

1. Step 1. Upload your receipt
    - Go to ```Data locker -> Files Manager```
    - Click on ```+ Add a file```
    - Upload tour photo and select ```File type``` as ```Receipts``` or ```Invoices``` in the dropdown, you can have the receipt as a PDF as well.
2. Step 2. Acknowledge custody
    - Go to ```Manufacturing -> Assemblies```
    - Select the impacted aircraft assembly, normally this should have a "*Parts need review*" status
    - Your component family should be avaialble on the left, click on the ```+ Acknowledge custody of new one``` button 
    - Select the appropriate Invoice Receipt, it should appear in the dropdown
    - Pick it and in the next wizard, give it a new Assembly code, and a friendly name
3. Step 3. Update Assembly
    - On the right hand side, you should see the missing components and additionally it should show e.g "1 available" 
    - Click on "Add to Assembly" to be added to the assembly
    - The assembly should be updated and the state of the assembly updated

### Result
The assembly status should now be complete

### Video Demonstration
{{< youtube ZPjMuc1Xmuo >}}
