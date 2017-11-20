---
title: 'Tutorial: Implementar la directiva | Documentos de Microsoft'
ms.custom: 
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 205760e2-9cd4-496f-93cd-0f93bc5d3231
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00c603a3a0c52d735441858af6a2f602c30d1f51
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-deploying-the-policy"></a><span data-ttu-id="2f4e0-102">Tutorial: Implementar la directiva</span><span class="sxs-lookup"><span data-stu-id="2f4e0-102">Walkthrough: Deploying the Policy</span></span>
<span data-ttu-id="2f4e0-103">Este tutorial proporciona instrucciones paso a paso para implementar la **ProcessPurchaseOrder** directiva en las tres formas siguientes:</span><span class="sxs-lookup"><span data-stu-id="2f4e0-103">This walkthrough provides step-by-step instructions for deploying the **ProcessPurchaseOrder** policy in the following three ways:</span></span>  
  
-   <span data-ttu-id="2f4e0-104">Exportación e importación de la directiva utilizando el Asistente para implementación de motor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-104">Exporting and importing the policy by using the Business Rules Engine Deployment Wizard.</span></span>  
  
-   <span data-ttu-id="2f4e0-105">Exportar la directiva a un archivo XML e importarla desde él en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-105">Exporting the policy to an XML file and importing the policy from an XML file by using the BizTalk Server Administration console.</span></span>  
  
-   <span data-ttu-id="2f4e0-106">Exportar la directiva como parte de un archivo MSI e importar éste último en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-106">Exporting the policy as part of an MSI file and importing the MSI file by using BizTalk Server Administration console.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2f4e0-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2f4e0-107">Prerequisites</span></span>  
 <span data-ttu-id="2f4e0-108">Debe completar la [Tutorial: ejecución de la directiva de seguimiento](../core/walkthrough-tracking-policy-execution.md) tutorial antes de llevar a cabo este tutorial.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-108">You must complete the [Walkthrough: Tracking Policy Execution](../core/walkthrough-tracking-policy-execution.md) walkthrough before performing this walkthrough.</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="2f4e0-109">Información general de este tutorial</span><span class="sxs-lookup"><span data-stu-id="2f4e0-109">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="2f4e0-110">Este tema contiene los tres tutoriales siguientes:</span><span class="sxs-lookup"><span data-stu-id="2f4e0-110">This topic  contains the following three walkthroughs:</span></span>  
  
1.  <span data-ttu-id="2f4e0-111">El primer tutorial contiene procedimientos para implementar la **ProcessPurchaseOrder** directiva utilizando el Asistente para implementación de motor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-111">The first walkthrough contains procedures for deploying the **ProcessPurchaseOrder** policy by using the Business Rules Engine Deployment Wizard.</span></span> <span data-ttu-id="2f4e0-112">En la tabla siguiente se describen los procedimientos de este tutorial.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-112">The following table describes the procedures in this walkthrough.</span></span>  
  
    |<span data-ttu-id="2f4e0-113">Título del procedimiento</span><span class="sxs-lookup"><span data-stu-id="2f4e0-113">Procedure title</span></span>|<span data-ttu-id="2f4e0-114">Descripción del procedimiento</span><span class="sxs-lookup"><span data-stu-id="2f4e0-114">Procedure description</span></span>|  
    |---------------------|---------------------------|  
    |<span data-ttu-id="2f4e0-115">Para exportar POVocabulary 1.0 y 1.1 mediante el Asistente para implementar el motor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="2f4e0-115">To export POVocabulary 1.0 and 1.1 by using the Business Rules Engine Deployment Wizard</span></span>|<span data-ttu-id="2f4e0-116">Proporciona instrucciones paso a paso para exportar las versiones 1.0 y 1.1 de la **POVocabulary** archivos vocabulario XML utilizando el Asistente para implementación de motor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-116">Provides step-by-step instructions for exporting versions 1.0 and 1.1 of the **POVocabulary** vocabulary to XML files by using the Business Rules Engine Deployment Wizard.</span></span>|  
    |<span data-ttu-id="2f4e0-117">Para exportar ProcessPurchaseOrder 1.3 mediante el Asistente para implementar el motor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="2f4e0-117">To export ProcessPurchaseOrder 1.3 by using the Business Rules Engine Deployment Wizard</span></span>|<span data-ttu-id="2f4e0-118">Proporciona instrucciones paso a paso para exportar la versión 1.3 de la **ProcessPurchaseOrder** directiva a un archivo XML utilizando el Asistente para implementación de motor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-118">Provides step-by-step instructions for exporting version 1.3 of the **ProcessPurchaseOrder** policy to an XML file by using the Business Rules Engine Deployment Wizard.</span></span>|  
    |<span data-ttu-id="2f4e0-119">Para eliminar ProcessPurchaseOrder y POVocabulary</span><span class="sxs-lookup"><span data-stu-id="2f4e0-119">To delete ProcessPurchaseOrder and POVocabulary</span></span>|<span data-ttu-id="2f4e0-120">Proporciona instrucciones paso a paso para eliminar la **ProcessPurchaseOrder** directiva y **POVocabulary** vocabulario para que pueda probar importando el archivo XML de archivos para volver a crearlos después.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-120">Provides step-by-step instructions for deleting the **ProcessPurchaseOrder** policy and **POVocabulary** vocabulary so that you can test importing the XML files to re-create them.</span></span>|  
    |<span data-ttu-id="2f4e0-121">Para importar desde XML a fin de volver a crear POVocabulary 1.0 y 1.1</span><span class="sxs-lookup"><span data-stu-id="2f4e0-121">To import from XML to re-create POVocabulary 1.0 and 1.1</span></span>|<span data-ttu-id="2f4e0-122">Proporciona instrucciones paso a paso para importar el archivo XML de vocabulario creado en el primer procedimiento para volver a crear la **POVocabulary** vocabulario.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-122">Provides step-by-step instructions for importing the vocabulary XML file you created in the first procedure to re-create the **POVocabulary** vocabulary.</span></span>|  
    |<span data-ttu-id="2f4e0-123">Para comprobar que se han vuelto a crear POVocabulary 1.0 y 1.1</span><span class="sxs-lookup"><span data-stu-id="2f4e0-123">To verify that POVocabulary 1.0 and 1.1 are re-created</span></span>|<span data-ttu-id="2f4e0-124">Proporciona instrucciones paso a paso para usar el Compositor de reglas de negocios para comprobar que las versiones 1.0 y 1.1 de **POVocabulary** se vuelven a crear.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-124">Provides step-by-step instructions for using the Business Rule Composer to verify that versions 1.0 and 1.1 of **POVocabulary** are re-created.</span></span>|  
    |<span data-ttu-id="2f4e0-125">Para importar desde XML a fin de volver a crear ProcessPurchaseOrder 1.3</span><span class="sxs-lookup"><span data-stu-id="2f4e0-125">To import from XML to re-create ProcessPurchaseOrder 1.3</span></span>|<span data-ttu-id="2f4e0-126">Proporciona instrucciones paso a paso para importar el archivo XML de directiva que creó en el segundo procedimiento para volver a crear la versión 1.3 de la **ProcessPurchaseOrder** directiva.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-126">Provides step-by-step instructions for importing the policy XML file you created in the second procedure to re-create version 1.3 of the **ProcessPurchaseOrder** policy.</span></span>|  
    |<span data-ttu-id="2f4e0-127">Para comprobar que se ha vuelto a crear ProcessPurchaseOrder 1.3</span><span class="sxs-lookup"><span data-stu-id="2f4e0-127">To verify that ProcessPurchaseOrder 1.3 is re-created</span></span>|<span data-ttu-id="2f4e0-128">Proporciona instrucciones paso a paso para usar el Compositor de reglas de negocios para comprobar que la versión 1.3 de la **ProcessPurchaseOrder** directiva se vuelve a crear.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-128">Provides step-by-step instructions for using the Business Rule Composer to verify that version 1.3 of the **ProcessPurchaseOrder** policy is re-created.</span></span>|  
  
2.  <span data-ttu-id="2f4e0-129">El segundo tutorial contiene procedimientos para implementar la **ProcessPurchaseOrder** directiva mediante un archivo XML exportado desde la consola de administración de BizTalk Server la siguiente tabla describen los procedimientos en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-129">The second walkthrough contains procedures for deploying the **ProcessPurchaseOrder** policy by using an XML file exported from the BizTalk Server Administration console The following table describes the procedures in this walkthrough.</span></span>  
  
    |<span data-ttu-id="2f4e0-130">Título del procedimiento</span><span class="sxs-lookup"><span data-stu-id="2f4e0-130">Procedure title</span></span>|<span data-ttu-id="2f4e0-131">Descripción del procedimiento</span><span class="sxs-lookup"><span data-stu-id="2f4e0-131">Procedure description</span></span>|  
    |---------------------|---------------------------|  
    |<span data-ttu-id="2f4e0-132">Para exportar la directiva ProcessPurchaseOrder 1.3 y el vocabulario POVocabulary a un archivo XML</span><span class="sxs-lookup"><span data-stu-id="2f4e0-132">To export the ProcessPurchaseOrder 1.3 policy and the POVocabulary vocabulary to an XML file</span></span>|<span data-ttu-id="2f4e0-133">Proporciona instrucciones paso a paso para usar la consola de administración de BizTalk Server para exportar la **ProcessPurchaseOrder** directiva y la **POVocabulary** vocabulario a un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-133">Provides step-by-step instructions for using the BizTalk Server Administration console to export the **ProcessPurchaseOrder** policy and the **POVocabulary** vocabulary to an XML file.</span></span>|  
    |<span data-ttu-id="2f4e0-134">Para eliminar la directiva ProcessPurchaseOrder</span><span class="sxs-lookup"><span data-stu-id="2f4e0-134">To delete the ProcessPurchaseOrder policy</span></span>|<span data-ttu-id="2f4e0-135">Proporciona instrucciones paso a paso para eliminar la **ProcessPurchaseOrder** directiva de **RuleTestApp** y la base de datos de motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-135">Provides step-by-step instructions for deleting the **ProcessPurchaseOrder** policy from **RuleTestApp** and the rule engine database.</span></span>|  
    |<span data-ttu-id="2f4e0-136">Para importar el archivo XML a fin de volver a crear la directiva ProcessPurchaseOrder</span><span class="sxs-lookup"><span data-stu-id="2f4e0-136">To import the XML file to re-create the ProcessPurchaseOrder policy</span></span>|<span data-ttu-id="2f4e0-137">Proporciona instrucciones paso a paso para importar el archivo XML exportado en el primer procedimiento para volver a crear la **ProcessPurchaseOrder** directiva.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-137">Provides step-by-step instructions for importing the XML file you exported in the first procedure to re-create the **ProcessPurchaseOrder** policy.</span></span>|  
    |<span data-ttu-id="2f4e0-138">Para agregar la directiva ProcessPurchaseOrder a la aplicación RuleTestApp </span><span class="sxs-lookup"><span data-stu-id="2f4e0-138">To add the ProcessPurchaseOrder policy to the RuleTestApp application</span></span>|<span data-ttu-id="2f4e0-139">Proporciona instrucciones paso a paso para agregar la **ProcessPurchaseOrder** directiva a la **RuleTestApp** aplicación.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-139">Provides step-by-step instructions for adding the **ProcessPurchaseOrder** policy to the **RuleTestApp** application.</span></span>|  
  
3.  <span data-ttu-id="2f4e0-140">El tercer tutorial contiene procedimientos para implementar la **ProcessPurchaseOrder** directiva mediante el uso de un archivo MSI exportado desde la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-140">The third walkthrough contains procedures for deploying the **ProcessPurchaseOrder** policy by using an MSI file exported from the BizTalk Server Administration console.</span></span> <span data-ttu-id="2f4e0-141">En la tabla siguiente se describen los procedimientos de este tutorial.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-141">The following table describes the procedures in this walkthrough.</span></span>  
  
    |<span data-ttu-id="2f4e0-142">Título del procedimiento</span><span class="sxs-lookup"><span data-stu-id="2f4e0-142">Procedure title</span></span>|<span data-ttu-id="2f4e0-143">El procedimiento contiene instrucciones paso a paso para</span><span class="sxs-lookup"><span data-stu-id="2f4e0-143">Procedure has step-by-step instructions for</span></span>|  
    |---------------------|---------------------------------------------------|  
    |<span data-ttu-id="2f4e0-144">Para exportar la aplicación RuleTestApp a un archivo MSI</span><span class="sxs-lookup"><span data-stu-id="2f4e0-144">To export the RuleTestApp application to an MSI file</span></span>|<span data-ttu-id="2f4e0-145">Proporciona instrucciones paso a paso para exportar la **RuleTestApp** aplicación a un archivo MSI, que se usará posteriormente para volver a crear la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-145">Provides step-by-step instructions for exporting the **RuleTestApp** application to an MSI file, which is used later to re-create the application.</span></span>|  
    |<span data-ttu-id="2f4e0-146">Para eliminar la aplicación RuleTestApp </span><span class="sxs-lookup"><span data-stu-id="2f4e0-146">To delete the RuleTestApp application</span></span>|<span data-ttu-id="2f4e0-147">Proporciona instrucciones paso a paso para eliminar la **RuleTestApp** aplicación para que pueda probar volver a crear la aplicación mediante el archivo MSI.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-147">Provides step-by-step instructions for deleting the **RuleTestApp** application so that you can test re-creating the application by using the MSI file.</span></span>|  
    |<span data-ttu-id="2f4e0-148">Para comprobar que la directiva ProcessPurchaseOrder y el vocabulario POVocabulary se han eliminado</span><span class="sxs-lookup"><span data-stu-id="2f4e0-148">To verify that the ProcessPurchaseOrder policy and POVocabulary vocabulary are deleted</span></span>|<span data-ttu-id="2f4e0-149">Proporciona instrucciones paso a paso para usar el Compositor de reglas de negocios para comprobar que la **ProcessPurchaseOrder** directiva y el vocabulario POVocabulary se eliminan.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-149">Provides step-by-step instructions for using the Business Rule Composer to verify that the **ProcessPurchaseOrder** policy and POVocabulary vocabulary are deleted.</span></span>|  
    |<span data-ttu-id="2f4e0-150">Para importar el archivo MSI a fin de volver a crear la aplicación RuleTestApp </span><span class="sxs-lookup"><span data-stu-id="2f4e0-150">To import the MSI file to re-create the RuleTestApp application</span></span>|<span data-ttu-id="2f4e0-151">Proporciona instrucciones paso a paso para usar la consola de administración de BizTalk Server para importar el archivo MSI para volver a crear la **RuleTestApp** aplicación.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-151">Provides step-by-step instructions for using the BizTalk Server Administration console to import the MSI file to re-create the **RuleTestApp** application.</span></span>|  
    |<span data-ttu-id="2f4e0-152">Para comprobar que la directiva ProcessPurchaseOrder se ha agregado a RuleTestApp </span><span class="sxs-lookup"><span data-stu-id="2f4e0-152">To verify that the ProcessPurchaseOrder policy is added to RuleTestApp</span></span>|<span data-ttu-id="2f4e0-153">Proporciona instrucciones paso a paso para usar la consola de administración de BizTalk Server para comprobar que la **ProcessPurchaseOrder** directiva se agregará a la **RuleTestApp** aplicación.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-153">Provides step-by-step instructions for using the BizTalk Server Administration console to verify that the **ProcessPurchaseOrder** policy is added to the **RuleTestApp** application.</span></span>|  
    |<span data-ttu-id="2f4e0-154">Para comprobar que la directiva ProcessPurchaseOrder y el vocabulario POVocabulary se han vuelto a crear</span><span class="sxs-lookup"><span data-stu-id="2f4e0-154">To verify that the ProcessPurchaseOrder policy and POVocabulary vocabulary are re-created</span></span>|<span data-ttu-id="2f4e0-155">Proporciona instrucciones paso a paso para usar el Compositor de reglas de negocios para comprobar que la **ProcessPurchaseOrder** directiva y **POVocabulary** vocabulario se vuelven a crear.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-155">Provides step-by-step instructions for using the Business Rule Composer to verify that the **ProcessPurchaseOrder** policy and **POVocabulary** vocabulary are re-created.</span></span>|  
    |<span data-ttu-id="2f4e0-156">Para probar la solución</span><span class="sxs-lookup"><span data-stu-id="2f4e0-156">To test the solution</span></span>|<span data-ttu-id="2f4e0-157">Proporciona instrucciones paso a paso para probar la solución.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-157">Provides step-by-step instructions for testing the solution.</span></span>|  
  
## <a name="procedures-for-deploying-the-processpurchaseorder-policy-by-using-the-business-rules-engine-deployment-wizard"></a><span data-ttu-id="2f4e0-158">Procedimientos para implementar la directiva ProcessPurchaseOrder mediante el Asistente para implementación de motor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="2f4e0-158">Procedures for Deploying the ProcessPurchaseOrder Policy by Using the Business Rules Engine Deployment Wizard</span></span>  
  
#### <a name="to-export-povocabulary-10-and-11-by-using-the-business-rules-engine-deployment-wizard"></a><span data-ttu-id="2f4e0-159">Para exportar POVocabulary 1.0 y 1.1 mediante el Asistente para implementar el motor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="2f4e0-159">To export POVocabulary 1.0 and 1.1 by using the Business Rules Engine Deployment Wizard</span></span>  
  
1.  <span data-ttu-id="2f4e0-160">En el **iniciar** menú Abrir **Asistente para implementación de motor de reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-160">On the **Start** menu, open **Business Rules Engine Deployment Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f4e0-161">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-161">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="2f4e0-162">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-162">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="2f4e0-163">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-163">Click **Next**.</span></span>  
  
3.  <span data-ttu-id="2f4e0-164">En el **la tarea de implementación** página, seleccione **Exportar directiva o vocabulario a archivo de base de datos**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-164">On the **Deployment Task** page, select **Export Policy/Vocabulary to file from database**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="2f4e0-165">En el **almacén de directivas** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-165">On the **Policy Store** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="2f4e0-166">En el **Exportar directiva o vocabulario** página, haga clic en **vocabulario**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-166">On the **Export Policy/Vocabulary** page, click **Vocabulary**.</span></span>  
  
6.  <span data-ttu-id="2f4e0-167">Seleccione **POVocabulary.1.0** en la lista desplegable de **directiva o vocabulario**, escriba o examine para especificar el nombre de archivo de salida XML como **C:\BRE-walkthroughs\POVocabulary10.xml**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-167">Select **POVocabulary.1.0** from the drop-down list for **Policy/Vocabulary**, type or browse to specify the XML output file name as **C:\BRE-walkthroughs\POVocabulary10.xml**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="2f4e0-168">En el **listo** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-168">On the **Ready** page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="2f4e0-169">En el **Exportar directiva o vocabulario** página, haga clic en **siguiente.**</span><span class="sxs-lookup"><span data-stu-id="2f4e0-169">On the **Exporting Policy/Vocabulary** page, click **Next.**</span></span>  
  
9. <span data-ttu-id="2f4e0-170">Seleccione **vuelva a ejecutar este asistente**y, a continuación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-170">Select **Run this wizard again**, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="2f4e0-171">Dado que seleccionó **vuelva a ejecutar este asistente**, la primera pantalla del asistente aparece de nuevo.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-171">Because you selected **Run this wizard again**, the first screen of the wizard appears again.</span></span>  
  
10. <span data-ttu-id="2f4e0-172">Repita los pasos 2 a 6.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-172">Repeat steps 2-6.</span></span>  
  
11. <span data-ttu-id="2f4e0-173">Seleccione **POVocabulary.1.1** en la lista desplegable de **directiva o vocabulario**, escriba o examine para especificar el nombre de archivo de salida XML como **C:\BRE-walkthroughs\POVocabulary11.xml**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-173">Select **POVocabulary.1.1** from the drop-down list for **Policy/Vocabulary**, type or browse to specify the XML output file name as **C:\BRE-walkthroughs\POVocabulary11.xml**, and then click **Next**.</span></span>  
  
12. <span data-ttu-id="2f4e0-174">Repita los pasos 8 y 9.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-174">Repeat steps 8 and 9.</span></span>  
  
13. <span data-ttu-id="2f4e0-175">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-175">Click **Finish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f4e0-176">Tiene que exportar las versiones 1.0 y 1.1 de **POVocabulary** porque **ProcessPurchaseOrder** 1.3 depende de las versiones de **POVocabulary**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-176">You need to export both version 1.0 and version 1.1 of **POVocabulary** because **ProcessPurchaseOrder** 1.3 depends on both versions of **POVocabulary**.</span></span> <span data-ttu-id="2f4e0-177">El **número máximo de elementos permitidos** se utiliza la definición de la versión 1.1 del vocabulario.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-177">The **Maximum number of items allowed** definition is used from version 1.1 of the vocabulary.</span></span> <span data-ttu-id="2f4e0-178">El **cantidad solicitada** y **estado de la solicitud** se usan las definiciones de la versión 1.0.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-178">The **Requested Quantity** and **Request Status** definitions are used from version 1.0.</span></span>  
  
#### <a name="to-export-processpurchaseorder-13-by-using-the-business-rule-engine-deployment-wizard"></a><span data-ttu-id="2f4e0-179">Para exportar ProcessPurchaseOrder 1.3 mediante el Asistente para implementación de motor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="2f4e0-179">To export ProcessPurchaseOrder 1.3 by using the Business Rule Engine Deployment Wizard</span></span>  
  
1.  <span data-ttu-id="2f4e0-180">En el **iniciar** menú Abrir **Asistente para implementación de motor de reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-180">On the **Start** menu, open **Business Rules Engine Deployment Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f4e0-181">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-181">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="2f4e0-182">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-182">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="2f4e0-183">En el **éste es el Asistente para la implementación del motor de reglas** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-183">On the **Welcome to the Rules Engine Deployment Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="2f4e0-184">Seleccione **Exportar directiva o vocabulario a archivo de base de datos**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-184">Select **Export Policy/Vocabulary to file from database**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="2f4e0-185">En el **almacén de directivas** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-185">On the **Policy Store** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="2f4e0-186">Compruebe que la **directiva** opción está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-186">Verify that the **Policy** option is selected.</span></span>  
  
6.  <span data-ttu-id="2f4e0-187">Seleccione **ProcessPurchaseOrder.1.3** en la lista desplegable de **directiva o vocabulario**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-187">Select **ProcessPurchaseOrder.1.3** from the drop-down list for **Policy/Vocabulary**.</span></span>  
  
7.  <span data-ttu-id="2f4e0-188">Escriba o examine para especificar **C:\BRE-walkthroughs\ProcessPOPolicy13.xml** como el nombre de archivo de salida XML.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-188">Type or browse to specify **C:\BRE-walkthroughs\ProcessPOPolicy13.xml** as the XML output file name.</span></span>  
  
8.  <span data-ttu-id="2f4e0-189">Haga clic en **siguiente** tres veces al y, a continuación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-189">Click **Next** thrice, and then click **Finish**.</span></span>  
  
#### <a name="to-delete-processpurchaseorder-and-povocabulary"></a><span data-ttu-id="2f4e0-190">Para eliminar ProcessPurchaseOrder y POVocabulary</span><span class="sxs-lookup"><span data-stu-id="2f4e0-190">To delete ProcessPurchaseOrder and POVocabulary</span></span>  
  
1.  <span data-ttu-id="2f4e0-191">En el **iniciar** menú Abrir **Compositor de reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-191">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="2f4e0-192">Si tiene el Compositor de reglas de negocio ya abrir, presione F5 o haga clic en **recarga** en el **archivo** menú para actualizarlo.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-192">If you have Business Rule Composer already open, press F5 or click **Reload** on the **File** menu to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f4e0-193">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-193">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="2f4e0-194">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-194">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="2f4e0-195">En la ventana Explorador de directivas, expanda **directivas**, expanda **ProcessPurchaseOrder**, haga clic en **versión 1.0**y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-195">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.0**, and then click **Delete**.</span></span> <span data-ttu-id="2f4e0-196">Si **eliminar** está deshabilitado, haga clic en **versión 1.0**y, a continuación, haga clic en **anular la implementación**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-196">If **Delete** is disabled, right-click **Version 1.0**, and then click **Undeploy**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f4e0-197">Las versiones de directivas implementadas no se pueden eliminar.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-197">The deployed policy versions cannot be deleted.</span></span> <span data-ttu-id="2f4e0-198">Es preciso anular la implementación de una directiva para poder eliminar una versión de esa directiva.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-198">You must undeploy a policy before deleting a policy version.</span></span>  
  
3.  <span data-ttu-id="2f4e0-199">Haga clic en **Sí** en el cuadro de mensaje de confirmación.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-199">Click **Yes** in the confirmation message box.</span></span>  
  
4.  <span data-ttu-id="2f4e0-200">Repita los pasos 2 y 3 para eliminar **versión 1.1**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-200">Repeat steps 2 and 3 to delete **Version 1.1**.</span></span>  
  
5.  <span data-ttu-id="2f4e0-201">Repita los pasos 2 y 3 para eliminar **versión 1.2**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-201">Repeat steps 2 and 3 to delete **Version 1.2**.</span></span>  
  
6.  <span data-ttu-id="2f4e0-202">Haga clic en **versión 1.3 implementada**y, a continuación, haga clic en **anular la implementación**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-202">Right-click **Version 1.3 - Deployed**, and then click **Undeploy**.</span></span> <span data-ttu-id="2f4e0-203">Si el **Undeploy** opción está deshabilitada, omita este paso.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-203">If the **Undeploy** option is disabled, ignore this step.</span></span>  
  
7.  <span data-ttu-id="2f4e0-204">En la ventana Explorador de hechos, expanda **vocabularios**, haga clic en **POVocabulary**y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-204">In the Facts Explorer window, expand **Vocabularies**, right-click **POVocabulary**, and then click **Delete**.</span></span>  
  
#### <a name="to-import-from-xml-to-re-create-povocabulary-10-and-11"></a><span data-ttu-id="2f4e0-205">Para importar desde XML a fin de volver a crear POVocabulary 1.0 y 1.1</span><span class="sxs-lookup"><span data-stu-id="2f4e0-205">To import from XML to re-create POVocabulary 1.0 and 1.1</span></span>  
  
1.  <span data-ttu-id="2f4e0-206">En el **iniciar** menú Abrir **Asistente para implementación de motor de reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-206">On the **Start** menu, open **Business Rules Engine Deployment Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f4e0-207">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-207">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="2f4e0-208">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-208">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="2f4e0-209">En el **éste es el Asistente para la implementación del motor de reglas**, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-209">On the **Welcome to the Rules Engine Deployment Wizard**, click **Next**.</span></span>  
  
3.  <span data-ttu-id="2f4e0-210">En el **la tarea de implementación** página, seleccione **importar y publicar la directiva o vocabulario a la base de datos desde un archivo**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-210">On the **Deployment Task** page, select **Import and publish Policy/Vocabulary to database from file**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="2f4e0-211">En el **almacén de directivas** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-211">On the **Policy Store** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="2f4e0-212">Busque y seleccione el **POVocabulary10.xml** archivo que creó en el primer procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-212">Browse and select the **POVocabulary10.xml** file you created in the first procedure.</span></span>  
  
6.  <span data-ttu-id="2f4e0-213">Haga clic en **abiertos** o haga doble clic en **POVocabulary10.xml**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-213">Click **Open** or double-click **POVocabulary10.xml**.</span></span>  
  
7.  <span data-ttu-id="2f4e0-214">Haga clic en **siguiente** en el Asistente para implementación de motor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-214">Click **Next** in the Business Rules Engine Deployment Wizard.</span></span>  
  
8.  <span data-ttu-id="2f4e0-215">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-215">Click **Next**.</span></span>  
  
9. <span data-ttu-id="2f4e0-216">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-216">Click **Next**.</span></span>  
  
10. <span data-ttu-id="2f4e0-217">Seleccione **vuelva a ejecutar este asistente**y, a continuación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-217">Select **Run this wizard again**, and then click **Finish**.</span></span>  
  
11. <span data-ttu-id="2f4e0-218">Repita los pasos del 2 al 9 para importar **POVocabulary11.xml**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-218">Repeat steps 2-9 to import **POVocabulary11.xml**.</span></span>  
  
12. <span data-ttu-id="2f4e0-219">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-219">Click **Finish**.</span></span>  
  
#### <a name="to-verify-that-povocabulary-10-and-11-are-re-created"></a><span data-ttu-id="2f4e0-220">Para comprobar que se han vuelto a crear POVocabulary 1.0 y 1.1</span><span class="sxs-lookup"><span data-stu-id="2f4e0-220">To verify that POVocabulary 1.0 and 1.1 are re-created</span></span>  
  
1.  <span data-ttu-id="2f4e0-221">En el **iniciar** menú Abrir **Compositor de reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-221">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="2f4e0-222">Si tiene ya está abierto, presione F5 o haga clic en **recarga** en el **archivo** menú para actualizarlo.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-222">If you have it already open, press F5 or click **Reload** on the **File** menu to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f4e0-223">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-223">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="2f4e0-224">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-224">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="2f4e0-225">En la ventana Explorador de hechos, haga clic en el **vocabularios** ficha.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-225">In the Facts Explorer window, click the **Vocabularies** tab.</span></span>  
  
3.  <span data-ttu-id="2f4e0-226">Expanda **vocabularios**, y debería ver **POVocabulary**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-226">Expand **Vocabularies**, and you should see **POVocabulary**.</span></span>  
  
4.  <span data-ttu-id="2f4e0-227">Expanda **POVocabulary**, y debería ver **versión 1.0** y **versión 1.1**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-227">Expand **POVocabulary**, and you should see **Version 1.0** and **Version 1.1**.</span></span>  
  
#### <a name="to-import-from-xml-to-re-create-processpurchaseorder-13"></a><span data-ttu-id="2f4e0-228">Para importar desde XML a fin de volver a crear ProcessPurchaseOrder 1.3</span><span class="sxs-lookup"><span data-stu-id="2f4e0-228">To import from XML to re-create ProcessPurchaseOrder 1.3</span></span>  
  
1.  <span data-ttu-id="2f4e0-229">En el **iniciar** menú Abrir **Asistente para implementación de motor de reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-229">On the **Start** menu, open **Business Rules Engine Deployment Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f4e0-230">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-230">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="2f4e0-231">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-231">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="2f4e0-232">En el **éste es el Asistente para la implementación del motor de reglas**, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-232">On the **Welcome to the Rules Engine Deployment Wizard**, click **Next**.</span></span>  
  
3.  <span data-ttu-id="2f4e0-233">En el **la tarea de implementación** página, seleccione **importar y publicar una directiva o vocabulario a la base de datos desde archivopara base de datos de archivo**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-233">On the **Deployment Task** page, select **Import and publish Policy/Vocabulary to database from fileto database from file**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="2f4e0-234">En el **almacén de directivas** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-234">On the **Policy Store** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="2f4e0-235">Busque y seleccione el **ProcessPOPolicy13.xml** archivo que creó anteriormente en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-235">Browse and select the **ProcessPOPolicy13.xml** file you created earlier in this walkthrough.</span></span>  
  
6.  <span data-ttu-id="2f4e0-236">Haga clic en **abiertos** o haga doble clic en **ProcessPOPolicy13.xml**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-236">Click **Open** or double-click **ProcessPOPolicy13.xml**.</span></span>  
  
7.  <span data-ttu-id="2f4e0-237">Haga clic en **siguiente** en el Asistente para implementación de motor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-237">Click **Next** in the Business Rules Engine Deployment Wizard.</span></span>  
  
8.  <span data-ttu-id="2f4e0-238">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-238">Click **Next**.</span></span>  
  
9. <span data-ttu-id="2f4e0-239">Haga clic en **Siguiente**y, a continuación, en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-239">Click **Next**, and then click **Finish**.</span></span>  
  
#### <a name="to-verify-that-processpurchaseorder-13-is-re-created"></a><span data-ttu-id="2f4e0-240">Para comprobar que se ha vuelto a crear ProcessPurchaseOrder 1.3</span><span class="sxs-lookup"><span data-stu-id="2f4e0-240">To verify that ProcessPurchaseOrder 1.3 is re-created</span></span>  
  
1.  <span data-ttu-id="2f4e0-241">En el **iniciar** menú Abrir **Compositor de reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-241">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="2f4e0-242">Si tiene ya está abierto, presione F5 o haga clic en **recarga** en el **archivo** menú para actualizarlo.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-242">If you have it already open, press F5 or click **Reload** on the **File** menu to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f4e0-243">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-243">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="2f4e0-244">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-244">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="2f4e0-245">En la ventana Explorador de directivas, expanda **directivas** y debería ver **ProcessPurchaseOrder**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-245">In the Policy Explorer window, expand **Policies** and you should see **ProcessPurchaseOrder**.</span></span>  
  
3.  <span data-ttu-id="2f4e0-246">Expanda **ProcessPurchaseOrder** y debería ver **versión 1.3 publicada**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-246">Expand **ProcessPurchaseOrder** and you should see **Version 1.3 - Published**.</span></span>  
  
## <a name="procedures-for-deploying-the-policy-by-using-an-xml-file-exported-from-the-biztalk-server-administration-console"></a><span data-ttu-id="2f4e0-247">Procedimientos para implementar la directiva mediante un archivo XML exportado desde la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="2f4e0-247">Procedures for Deploying the Policy by Using an XML file Exported from the BizTalk Server Administration Console</span></span>  
  
#### <a name="to-export-the-processpurchaseorder-13-policy-and-the-povocabulary-vocabulary-to-an-xml-file"></a><span data-ttu-id="2f4e0-248">Para exportar la directiva ProcessPurchaseOrder 1.3 y el vocabulario POVocabulary a un archivo XML</span><span class="sxs-lookup"><span data-stu-id="2f4e0-248">To export the ProcessPurchaseOrder 1.3 policy and the POVocabulary vocabulary to an XML file</span></span>  
  
1.  <span data-ttu-id="2f4e0-249">En el **iniciar** menú Abrir [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f4e0-249">On the **Start** menu, open [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span> <span data-ttu-id="2f4e0-250">Si la herramienta ya está abierta, presione F5 para actualizarla.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-250">If you have the tool already open, press F5 to refresh it.</span></span>  
  
2.  <span data-ttu-id="2f4e0-251">Expanda **raíz de consola**, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda **RuleTestApp** .</span><span class="sxs-lookup"><span data-stu-id="2f4e0-251">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, expand **Applications**, and then expand **RuleTestApp**.</span></span>  
  
3.  <span data-ttu-id="2f4e0-252">Haga clic en **directivas** y asegúrese de que ve la directiva ProcessPurchaseOrder 1.3 de la lista.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-252">Click **Policies** and make sure that you see the ProcessPurchaseOrder 1.3 policy in the list.</span></span>  
  
4.  <span data-ttu-id="2f4e0-253">Haga clic en **ProcessPurchaseOrder**y, a continuación, haga clic en **exportar**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-253">Right-click **ProcessPurchaseOrder**, and then click **Export**.</span></span>  
  
5.  <span data-ttu-id="2f4e0-254">En el **exportar directivas** diálogo cuadro, asegúrese de que el **ProcessPurchaseOrder** directiva y la **POVocabulary** están seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-254">In the **Export Policies** dialog box, make sure the **ProcessPurchaseOrder** policy and the **POVocabulary** are selected.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f4e0-255">Puede exportar todas las directivas en una aplicación en un archivo XML con el botón secundario **RuleTest** y, a continuación, haga clic en **exportar** en el **directivas** menú.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-255">You can export all the policies in an application to an XML file by right-clicking **RuleTest** and then clicking **Export** on the **Policies** menu.</span></span> <span data-ttu-id="2f4e0-256">De este modo, se exportan todas las directivas y el vocabulario usados por esta aplicación a un mismo archivo XML.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-256">This way you can export all the policies and vocabulary used by this application to a single XML file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f4e0-257">Puede exportar todas las directivas de todas las aplicaciones en un archivo XML haciendo clic en el **aplicaciones** nodo y, a continuación, haga clic en **exportar** en el **directivas** menú.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-257">You can export all the policies in all the applications to an XML file by right-clicking the **Applications** node and then clicking **Export** on the **Policies** menu.</span></span> <span data-ttu-id="2f4e0-258">De este modo, se exportan todas las directivas y vocabularios usados en todas las aplicaciones a un mismo archivo XML.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-258">This way you can export all the policies and vocabularies used by all the applications into a single XML file.</span></span>  
  
6.  <span data-ttu-id="2f4e0-259">Especifique un nombre de archivo de salida XML (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-259">Specify an output XML file name (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**), and then click **Ok**.</span></span>  
  
#### <a name="to-delete-the-processpurchaseorder-policy"></a><span data-ttu-id="2f4e0-260">Para eliminar la directiva ProcessPurchaseOrder</span><span class="sxs-lookup"><span data-stu-id="2f4e0-260">To delete the ProcessPurchaseOrder policy</span></span>  
  
1.  <span data-ttu-id="2f4e0-261">En administración de BizTalk Server, haga clic en **ProcessPurchaseOrder** en la lista y, a continuación, haga clic en **quitar**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-261">In BizTalk Server Administration, right-click **ProcessPurchaseOrder** in the list, and then click **Remove**.</span></span>  
  
2.  <span data-ttu-id="2f4e0-262">Haga clic en **Sí** en el **Quitar directiva** cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-262">Click **Yes** in the **Remove Policy** message box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f4e0-263">Si la directiva está en estado implementado, no se puede quitar.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-263">If the policy is in the deployed state, it cannot be removed.</span></span> <span data-ttu-id="2f4e0-264">Haga clic en **ProcessPurchaseOrder**y, a continuación, haga clic en **Undeploy** anular la implementación de la directiva.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-264">Right-click **ProcessPurchaseOrder**, and then click **Undeploy** to undeploy the policy.</span></span> <span data-ttu-id="2f4e0-265">El **quitar** elemento de menú está disponible cuando la directiva está implementada.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-265">The **Remove** menu item is available when the policy is undeployed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f4e0-266">Los vocabularios en el que el **ProcessPurchaseOrder** directiva depende, en este caso **POVocabulary**, también se eliminan.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-266">The vocabularies on which the **ProcessPurchaseOrder** policy depends, in this case **POVocabulary**, are also deleted.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f4e0-267">Cuando se quita una directiva de una aplicación, tanto la directiva como los vocabularios de los que depende se eliminan asimismo de la base de datos del motor de reglas, no sólo de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-267">When you remove a policy from an application, the policy and the vocabularies that it depends on are deleted from the rule engine database as well, not just from the application.</span></span>  
  
#### <a name="to-import-the-xml-file-to-re-create-the-processpurchaseorder-policy"></a><span data-ttu-id="2f4e0-268">Para importar el archivo XML a fin de volver a crear la directiva ProcessPurchaseOrder</span><span class="sxs-lookup"><span data-stu-id="2f4e0-268">To import the XML file to re-create the ProcessPurchaseOrder policy</span></span>  
  
1.  <span data-ttu-id="2f4e0-269">En administración de BizTalk Server, expanda **raíz de consola**, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]y, a continuación, expanda **grupo de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-269">In BizTalk Server Administration, expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then expand **BizTalk Group**.</span></span>  
  
2.  <span data-ttu-id="2f4e0-270">Haga clic en **aplicaciones**, seleccione **importación**y, a continuación, haga clic en **directivas**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-270">Right-click **Applications**, point to **Import**, and then click **Policies**.</span></span>  
  
3.  <span data-ttu-id="2f4e0-271">Busque y haga doble clic en el archivo XML (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**) que creó en el primer procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-271">Browse, and double-click the XML file (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**) that you created in the first procedure.</span></span>  
  
4.  <span data-ttu-id="2f4e0-272">Expanda  **\<todos los artefactos >** en **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-272">Expand **\<All Artifacts>** under **Applications**.</span></span>  
  
5.  <span data-ttu-id="2f4e0-273">Haga clic en **directivas**, verá la versión 1.3 de la **ProcessPurchaseOrder** directiva en la lista.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-273">Click **Policies**, and you should see version 1.3 of the **ProcessPurchaseOrder** policy in the list.</span></span>  
  
6.  <span data-ttu-id="2f4e0-274">Presione F5 para actualizar la vista.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-274">Press F5 to refresh the view.</span></span> <span data-ttu-id="2f4e0-275">El **ProcessPurchaseOrder** directiva debe estar en el **no publica** estado.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-275">The **ProcessPurchaseOrder** policy should be in the **Not Published** state.</span></span>  
  
#### <a name="to-add-the-processpurchaseorder-policy-to-the-ruletestapp-application"></a><span data-ttu-id="2f4e0-276">Para agregar la directiva ProcessPurchaseOrder a la aplicación RuleTestApp </span><span class="sxs-lookup"><span data-stu-id="2f4e0-276">To add the ProcessPurchaseOrder policy to the RuleTestApp application</span></span>  
  
1.  <span data-ttu-id="2f4e0-277">En administración de BizTalk Server, haga clic en **ProcessPurchaseOrder** directiva y, a continuación, haga clic en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-277">In BizTalk Server Administration, right-click **ProcessPurchaseOrder** policy, and then click **Publish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f4e0-278">Sólo se pueden agregar a una aplicación de BizTalk las directivas publicadas.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-278">Only published policies can be added to a BizTalk application.</span></span>  
  
2.  <span data-ttu-id="2f4e0-279">En el **aplicaciones** nodo, expanda **RuleTestApp**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-279">In the **Applications** node, expand **RuleTestApp**.</span></span>  
  
3.  <span data-ttu-id="2f4e0-280">Haga clic en **directivas** en **RuleTestApp**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-280">Click **Policies** in **RuleTestApp**.</span></span>  
  
4.  <span data-ttu-id="2f4e0-281">Haga clic en la lista de la derecha, seleccione **agregar**y, a continuación, haga clic en **directiva**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-281">Right-click in the list on the right, point to **Add**, and then click **Policy**.</span></span>  
  
5.  <span data-ttu-id="2f4e0-282">Expanda el **ProcessPurchaseOrder** nodo, seleccione la casilla de verificación **versión 1.3 (publicada)**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-282">Expand the **ProcessPurchaseOrder** node, select the check box for **Version 1.3 (Published)**, and then click **OK**.</span></span> <span data-ttu-id="2f4e0-283">.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-283">.</span></span>  
  
6.  <span data-ttu-id="2f4e0-284">Haga clic en **ProcessPurchaseOrder**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-284">Right-click **ProcessPurchaseOrder**, and then click **Deploy**.</span></span> <span data-ttu-id="2f4e0-285">Si no ve **ProcessPurchaseOrder** en la lista, presione F5 para actualizar la vista.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-285">If you do not see **ProcessPurchaseOrder** in the list, press F5 to refresh the view.</span></span>  
  
7.  <span data-ttu-id="2f4e0-286">Haga clic en **Sí** en el cuadro de mensaje de confirmación.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-286">Click **Yes** in the confirmation message box.</span></span>  
  
## <a name="procedures-for-deploying-the-policy-by-using-an-msi-file"></a><span data-ttu-id="2f4e0-287">Procedimientos para implementar la directiva mediante un archivo MSI</span><span class="sxs-lookup"><span data-stu-id="2f4e0-287">Procedures for Deploying the Policy by Using an MSI File</span></span>  
  
#### <a name="to-export-the-ruletestapp-application-to-an-msi-file"></a><span data-ttu-id="2f4e0-288">Para exportar la aplicación RuleTestApp a un archivo MSI</span><span class="sxs-lookup"><span data-stu-id="2f4e0-288">To export the RuleTestApp application to an MSI file</span></span>  
  
1.  <span data-ttu-id="2f4e0-289">En el **iniciar** menú Abrir **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-289">On the **Start** menu, open **BizTalk Server Administration**.</span></span> <span data-ttu-id="2f4e0-290">Si la herramienta ya está abierta, presione F5 para actualizarla.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-290">If you have the tool already open, press F5 to refresh it.</span></span>  
  
2.  <span data-ttu-id="2f4e0-291">Expanda **raíz de consola**, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-291">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="2f4e0-292">Haga clic en **RuleTestApp**, seleccione **exportar**y, a continuación, haga clic en **archivo MSI**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-292">Right-click **RuleTestApp**, point to **Export**, and then click **MSI file**.</span></span>  
  
4.  <span data-ttu-id="2f4e0-293">En el **éste es el Asistente para exportar archivos MSI** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-293">On the **Welcome to the Export MSI File Wizard** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="2f4e0-294">En el **seleccionar recursos** página, revise todas las opciones predeterminadas y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-294">On the **Select Resources** page, review all the default options, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="2f4e0-295">En el **especificar Hosts de ISS** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-295">On the **Specify IIS Hosts** page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="2f4e0-296">En el **dependencias** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-296">On the **Dependencies** page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="2f4e0-297">En el **destino** página, especifique el directorio y el nombre del archivo msi **C:\BRE-Walkthroughs\RuleTestApp.msi**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-297">On the **Destination** page, specify the directory and name for the MSI as **C:\BRE-Walkthroughs\RuleTestApp.msi**.</span></span>  
  
9. <span data-ttu-id="2f4e0-298">Haga clic en **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-298">Click **Export**.</span></span>  
  
10. <span data-ttu-id="2f4e0-299">En el **resumen** página, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-299">On the **Summary** page, click **Finish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f4e0-300">Al exportar la aplicación RuleTestApp, las directivas y los vocabularios usados en esa aplicación también se exportan al archivo MSI.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-300">When you export the RuleTestApp application, the policies and vocabularies used by the application are also exported in the MSI file.</span></span> <span data-ttu-id="2f4e0-301">Posteriormente, cuando importe el archivo MSI, se volverán a crear el vocabulario, la directiva y la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-301">Later, when you import the MSI file, the vocabulary, policy, and application are all re-created.</span></span>  
  
#### <a name="to-delete-the-ruletestapp-application"></a><span data-ttu-id="2f4e0-302">Para eliminar la aplicación RuleTestApp </span><span class="sxs-lookup"><span data-stu-id="2f4e0-302">To delete the RuleTestApp application</span></span>  
  
1.  <span data-ttu-id="2f4e0-303">En administración de BizTalk Server, haga clic en **RuleTestApp**y compruebe si el **eliminar** menú está habilitado o deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-303">In BizTalk Server Administration, right-click **RuleTestApp**, and check if the **Delete** menu is enabled or disabled.</span></span>  
  
2.  <span data-ttu-id="2f4e0-304">Si **eliminar** está deshabilitado, haga clic en **RuleTestApp**, haga clic en **detener**, seleccione **detención completa: finalizar instancia**y, a continuación, haga clic en  **Detener**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-304">If **Delete** is disabled, right-click **RuleTestApp**, click **Stop**, select **Full Stop - Terminate Instance**, and then click **Stop**.</span></span>  
  
3.  <span data-ttu-id="2f4e0-305">Haga clic en **RuleTestApp**y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-305">Right-click **RuleTestApp**, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="2f4e0-306">Haga clic en **Sí** para confirmar la eliminación.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-306">Click **Yes** to confirm deletion.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f4e0-307">Cuando se elimina una aplicación, todas las directivas de la aplicación y los vocabularios dependientes se eliminan asimismo de la base de datos del motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-307">When you delete an application, all the policies in the application and dependent vocabularies are deleted from the rule engine database as well.</span></span>  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-and-povocabulary-vocabulary-are-deleted"></a><span data-ttu-id="2f4e0-308">Para comprobar que la directiva ProcessPurchaseOrder y el vocabulario POVocabulary se han eliminado</span><span class="sxs-lookup"><span data-stu-id="2f4e0-308">To verify that the ProcessPurchaseOrder policy and POVocabulary vocabulary are deleted</span></span>  
  
1.  <span data-ttu-id="2f4e0-309">En el **iniciar** menú Abrir **Compositor de reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-309">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="2f4e0-310">Si tienes Compositor de reglas de negocio ya abierto, presione F5 para actualizarla.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-310">If you have Business Rule Composer already open, press F5 to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f4e0-311">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-311">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="2f4e0-312">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-312">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="2f4e0-313">En la ventana Explorador de directivas, expanda **directivas**y asegúrese de que la directiva ProcessPurchaseOrder no existe.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-313">In the Policy Explorer window, expand **Policies**, and make sure that the ProcessPurchaseOrder policy does not exist.</span></span>  
  
3.  <span data-ttu-id="2f4e0-314">En la ventana Explorador de hechos, expanda **vocabularios**y asegúrese de que POVocabulary no existe.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-314">In the Facts Explorer window, expand **Vocabularies**, and make sure that POVocabulary does not exist.</span></span>  
  
#### <a name="to-import-the-msi-file-to-re-create-the-ruletestapp-application"></a><span data-ttu-id="2f4e0-315">Para importar el archivo MSI a fin de volver a crear la aplicación RuleTestApp </span><span class="sxs-lookup"><span data-stu-id="2f4e0-315">To import the MSI file to re-create the RuleTestApp application</span></span>  
  
1.  <span data-ttu-id="2f4e0-316">En el **iniciar** menú Abrir **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-316">On the **Start** menu, open **BizTalk Server Administration**.</span></span> <span data-ttu-id="2f4e0-317">Si la consola de administración de BizTalk Server ya está abierta, presione F5 para actualizarla.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-317">If you have the BizTalk Server Administration console already open, press F5 to refresh it.</span></span>  
  
2.  <span data-ttu-id="2f4e0-318">Expanda **raíz de consola**, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]y, a continuación, expanda **grupo de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-318">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then expand **BizTalk Group**.</span></span>  
  
3.  <span data-ttu-id="2f4e0-319">Haga clic en **aplicaciones**, seleccione **importación**y, a continuación, haga clic en **archivo MSI**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-319">Right-click **Applications**, point to **Import**, and then click **MSI file**.</span></span>  
  
4.  <span data-ttu-id="2f4e0-320">En el **Asistente para importar** página, busque y seleccione el archivo MSI (RuleTestApp.msi) que exportó anteriormente para la **archivo MSI para importar** configuración.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-320">On the **Welcome to the Import Wizard** page, browse and select the MSI file (RuleTestApp.msi) you exported earlier for the **MSI file to import** setting.</span></span>  
  
5.  <span data-ttu-id="2f4e0-321">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-321">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="2f4e0-322">En el **configuración de la aplicación** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-322">On the **Application Settings** page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="2f4e0-323">En el **configuración del entorno de destino de aplicación** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-323">On the **Application Target Environment Settings** page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="2f4e0-324">En el **resumen de importación** página, haga clic en **importación**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-324">On the **Import Summary** page, click **Import**.</span></span>  
  
9. <span data-ttu-id="2f4e0-325">En el **importación se realizó correctamente** página, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-325">On the **Import Succeeded** page, click **Finish**.</span></span> <span data-ttu-id="2f4e0-326">Debería ver que la **RuleTestApp** aplicación se crea en **aplicaciones** en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-326">You should see that the **RuleTestApp** application is created under **Applications** in the BizTalk Server Administration console.</span></span>  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-is-added-to-ruletestapp"></a><span data-ttu-id="2f4e0-327">Para comprobar que la directiva ProcessPurchaseOrder se ha agregado a RuleTestApp </span><span class="sxs-lookup"><span data-stu-id="2f4e0-327">To verify that the ProcessPurchaseOrder policy is added to RuleTestApp</span></span>  
  
1.  <span data-ttu-id="2f4e0-328">Expanda **RuleTestApp** en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-328">Expand **RuleTestApp** in the BizTalk Server Administration console.</span></span>  
  
2.  <span data-ttu-id="2f4e0-329">Seleccione **directivas** y debería ver **ProcessPurchaseOrder** en la lista en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-329">Select **Policies** and you should see **ProcessPurchaseOrder** in the list in the right pane.</span></span>  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-and-povocabulary-vocabulary-are-re-created"></a><span data-ttu-id="2f4e0-330">Para comprobar que la directiva ProcessPurchaseOrder y el vocabulario POVocabulary se han vuelto a crear</span><span class="sxs-lookup"><span data-stu-id="2f4e0-330">To verify that the ProcessPurchaseOrder policy and POVocabulary vocabulary are re-created</span></span>  
  
1.  <span data-ttu-id="2f4e0-331">En el **iniciar** menú Abrir **Compositor de reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-331">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="2f4e0-332">Si ya está abierto, presione F5 para actualizarlo.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-332">If you have it already open, press F5 to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f4e0-333">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-333">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="2f4e0-334">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-334">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="2f4e0-335">En la ventana Explorador de directivas, expanda **directivas**y asegúrese de que **ProcessPurchaseOrder** existe.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-335">In the Policy Explorer window, expand **Policies**, and make sure that **ProcessPurchaseOrder** exists.</span></span>  
  
3.  <span data-ttu-id="2f4e0-336">En la ventana Explorador de hechos, expanda **vocabularios**y asegúrese de que **POVocabulary** existe.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-336">In the Facts Explorer window, expand **Vocabularies**, and make sure that **POVocabulary** exists.</span></span>  
  
#### <a name="to-test-the-solution"></a><span data-ttu-id="2f4e0-337">Para probar la solución</span><span class="sxs-lookup"><span data-stu-id="2f4e0-337">To test the solution</span></span>  
  
1.  <span data-ttu-id="2f4e0-338">En el **iniciar** menú Abrir **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-338">On the **Start** menu, open **BizTalk Server Administration**.</span></span> <span data-ttu-id="2f4e0-339">Si la consola de administración de BizTalk Server ya está abierta, presione F5 para actualizarla.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-339">If you have the BizTalk Server Administration console already open, press F5 to refresh it.</span></span>  
  
2.  <span data-ttu-id="2f4e0-340">Expanda **raíz de consola**, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-340">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="2f4e0-341">Haga clic en **RuleTestApp**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-341">Right-click **RuleTestApp**, and then click **Start**.</span></span>  
  
4.  <span data-ttu-id="2f4e0-342">Haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-342">Click **Start**.</span></span>  
  
5.  <span data-ttu-id="2f4e0-343">Copia **SamplePO.xml** que creó en [Tutorial: probar la directiva](../core/walkthrough-testing-the-policy.md) al directorio de entrada para la orquestación.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-343">Copy **SamplePO.xml** that you created in [Walkthrough: Testing the Policy](../core/walkthrough-testing-the-policy.md) to the input directory for the orchestration.</span></span>  
  
6.  <span data-ttu-id="2f4e0-344">Debería ver un archivo de salida en el directorio de salida de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-344">You should see an output file in the output directory for the orchestration.</span></span> <span data-ttu-id="2f4e0-345">Abra el archivo XML de salida y observe que el valor de la **estado** campo está establecido en **aprobado**.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-345">Open the output XML file and notice that the value of the **Status** field is set to **Approved**.</span></span>  
  
7.  <span data-ttu-id="2f4e0-346">Repita los pasos 3 y 4 con **SamplePO2.xml**y observe que el valor de la **estado** campo en el documento de salida es el mismo que el documento de entrada (**XYZ**).</span><span class="sxs-lookup"><span data-stu-id="2f4e0-346">Repeat steps 3 and 4 with **SamplePO2.xml**, and notice that the value of the **Status** field in the output document is the same as in the input document (**XYZ**).</span></span>  
  
## <a name="comments"></a><span data-ttu-id="2f4e0-347">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2f4e0-347">Comments</span></span>  
  
-   <span data-ttu-id="2f4e0-348">Es **muy importante** recordar que, cuando se quita una directiva desde una aplicación, no solo quita la asociación entre la aplicación y la directiva sino que elimina la directiva y su vocabulario asociado de la regla base de datos de motor.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-348">It is **very important** to remember that when you remove a policy from an application, you do not just remove the association between the application and the policy; you also delete the policy and its associated vocabulary from the rule engine database.</span></span>  
  
-   <span data-ttu-id="2f4e0-349">Al iniciar una aplicación, ésta implementa de manera predeterminada y automática todas las directivas.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-349">When you start an application, by default, it deploys the policies automatically.</span></span> <span data-ttu-id="2f4e0-350">De forma similar, al detener una aplicación y seleccionar **detención completa: finalizar instancias**, las directivas asociadas se anula automáticamente.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-350">Similarly, when you stop an application and select **Full Stop - Terminate Instances**, the associated policies are undeployed automatically.</span></span> <span data-ttu-id="2f4e0-351">Cuando se selecciona **detención parcial: suspender las instancias en ejecución**, las directivas asociadas no se anula automáticamente.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-351">When you select **Partial Stop - Suspend running instances**, the associated policies are not undeployed automatically.</span></span>  
  
-   <span data-ttu-id="2f4e0-352">Debe actualizar las vistas del Compositor de reglas de negocio y de la consola de administración de BizTalk Server para asegurarse de estar viendo la información más reciente antes de llevar a cabo cualquier operación.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-352">You should refresh the views in Business Rule Composer and BizTalk Server Administration console to make sure you are looking at the latest information before performing any operation.</span></span>  
  
-   <span data-ttu-id="2f4e0-353">Si crea una versión nueva de la directiva cuya versión anterior está asociada a una aplicación de BizTalk, debe agregar manualmente a la aplicación la nueva versión de la directiva.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-353">If you create a new version of the policy whose earlier version is associated with a BizTalk application, you should manually add the new version of the policy to the application.</span></span> <span data-ttu-id="2f4e0-354">No debe quitar la versión anterior de la directiva a no ser que desee eliminarla por completo de la base de datos del motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-354">You should not remove the old version of the policy unless you really want to delete it from the rule engine database.</span></span>  
  
-   <span data-ttu-id="2f4e0-355">Puede combinar dos o más archivos BRL (archivos XML de Lenguaje de reglas de negocio) en un solo archivo BRL antes de importar.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-355">You can merge two or more BRL (Business Rule Language XML file) files into a single BRL file before importing.</span></span> <span data-ttu-id="2f4e0-356">El código siguiente muestra tres archivos BRL.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-356">The following code shows three BRL files.</span></span> <span data-ttu-id="2f4e0-357">El primer archivo BRL contiene el **POVocabulary** vocabulario.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-357">The first BRL file contains the **POVocabulary** vocabulary.</span></span> <span data-ttu-id="2f4e0-358">El segundo archivo BRL contiene el **ProcessPurchaseOrder** directiva.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-358">The second BRL file contains the **ProcessPurchaseOrder** policy.</span></span> <span data-ttu-id="2f4e0-359">El tercer archivo BRL contiene el **POVocabulary** vocabulario y **ProcessPurchaseOrder** directiva.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-359">The third BRL file contains both the **POVocabulary** vocabulary and the **ProcessPurchaseOrder** policy.</span></span> <span data-ttu-id="2f4e0-360">Para realizar el tercer archivo BRL, realice estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2f4e0-360">The third BRE file is created by performing the following steps:</span></span>  
  
    1.  <span data-ttu-id="2f4e0-361">Cree un archivo nuevo con cualquier archivo de editor y guardarla como un archivo XML (por ejemplo: POPolicyVocabulary.xml).</span><span class="sxs-lookup"><span data-stu-id="2f4e0-361">Create a new file using any file editor and save it as an XML file (for example: POPolicyVocabulary.xml).</span></span>  
  
    2.  <span data-ttu-id="2f4e0-362">Copie el contenido XML completo del primer archivo BRL que contiene el vocabulario.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-362">Copy the entire XML content from the first BRL file containing the vocabulary.</span></span>  
  
    3.  <span data-ttu-id="2f4e0-363">Copie el bloque de conjunto de reglas (comienza con la \<ruleset > etiqueta y finaliza con el \</ruleset > etiqueta) del segundo archivo BRL.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-363">Copy the ruleset block (starts with the \<ruleset> tag and ends with the \</ruleset> tag) from the second BRL file.</span></span>  
  
    4.  <span data-ttu-id="2f4e0-364">Guarde el archivo nuevo.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-364">Save the new file.</span></span> <span data-ttu-id="2f4e0-365">Puede importar este archivo XML único para crear el **POVocabulary** vocabulario y **ProcessPurchaseOrder** directiva.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-365">You can import this single XML file to create the **POVocabulary** vocabulary and the **ProcessPurchaseOrder** policy.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f4e0-366">El orden en que se enumeran los nodos vocabulary y ruleset en el archivo BRL combinado no es relevante.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-366">It does not matter in which order the vocabulary and ruleset nodes are listed in the merged BRL file.</span></span> <span data-ttu-id="2f4e0-367">Puede colocar el nodo ruleset antes que el nodo vocabulary.</span><span class="sxs-lookup"><span data-stu-id="2f4e0-367">You can have the ruleset node ahead of the vocabulary node.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <brl  
    xmlns="http://schemas.microsoft.com/businessruleslanguage/2002">  
      <vocabulary id="e588676a-ba01-4f37-b59d-91f7e1eb1f1a" name="POVocabulary" uri="" description="">  
           ……   
      </vocabulary>  
    </brl>  
  
    <?xml version="1.0" encoding="utf-8"?>  
    <brl  
    xmlns="http://schemas.microsoft.com/businessruleslanguage/2002">  
      <ruleset name="ProcessPurchaseOrder">  
         ……  
      </ruleset>  
    </brl>  
  
    <brl  
    xmlns="http://schemas.microsoft.com/businessruleslanguage/2002">  
      <vocabulary id="e588676a-ba01-4f37-b59d-91f7e1eb1f1a" name="POVocabulary" uri="" description="">  
           ……   
      </vocabulary>  
      <ruleset name="ProcessPurchaseOrder">  
         ……  
      </ruleset>  
    </brl>  
    ```