---
title: 'Tutorial: Implementar la directiva | Microsoft Docs'
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 205760e2-9cd4-496f-93cd-0f93bc5d3231
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b35b7d9c3b2b7780ef87b0dedae52f58c20dc835
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996301"
---
# <a name="walkthrough-deploying-the-policy"></a><span data-ttu-id="d6fbc-102">Tutorial: Implementar la directiva</span><span class="sxs-lookup"><span data-stu-id="d6fbc-102">Walkthrough: Deploying the Policy</span></span>
<span data-ttu-id="d6fbc-103">Este tutorial proporciona instrucciones paso a paso para implementar la **ProcessPurchaseOrder** directiva en las tres formas siguientes:</span><span class="sxs-lookup"><span data-stu-id="d6fbc-103">This walkthrough provides step-by-step instructions for deploying the **ProcessPurchaseOrder** policy in the following three ways:</span></span>  
  
-   <span data-ttu-id="d6fbc-104">Exportación e importación de la directiva utilizando el Asistente para implementación de motor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-104">Exporting and importing the policy by using the Business Rules Engine Deployment Wizard.</span></span>  
  
-   <span data-ttu-id="d6fbc-105">Exportar la directiva a un archivo XML e importarla desde él en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-105">Exporting the policy to an XML file and importing the policy from an XML file by using the BizTalk Server Administration console.</span></span>  
  
-   <span data-ttu-id="d6fbc-106">Exportar la directiva como parte de un archivo MSI e importar éste último en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-106">Exporting the policy as part of an MSI file and importing the MSI file by using BizTalk Server Administration console.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d6fbc-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d6fbc-107">Prerequisites</span></span>  
 <span data-ttu-id="d6fbc-108">Debe completar el [Tutorial: ejecución de la directiva de seguimiento](../core/walkthrough-tracking-policy-execution.md) tutorial antes de realizar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-108">You must complete the [Walkthrough: Tracking Policy Execution](../core/walkthrough-tracking-policy-execution.md) walkthrough before performing this walkthrough.</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="d6fbc-109">Información general de este tutorial</span><span class="sxs-lookup"><span data-stu-id="d6fbc-109">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="d6fbc-110">Este tema contiene los tres tutoriales siguientes:</span><span class="sxs-lookup"><span data-stu-id="d6fbc-110">This topic  contains the following three walkthroughs:</span></span>  
  
1.  <span data-ttu-id="d6fbc-111">El primer tutorial contiene procedimientos para implementar la **ProcessPurchaseOrder** directiva utilizando el Asistente para implementación de motor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-111">The first walkthrough contains procedures for deploying the **ProcessPurchaseOrder** policy by using the Business Rules Engine Deployment Wizard.</span></span> <span data-ttu-id="d6fbc-112">En la tabla siguiente se describen los procedimientos de este tutorial.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-112">The following table describes the procedures in this walkthrough.</span></span>  
  
    |<span data-ttu-id="d6fbc-113">Título del procedimiento</span><span class="sxs-lookup"><span data-stu-id="d6fbc-113">Procedure title</span></span>|<span data-ttu-id="d6fbc-114">Descripción del procedimiento</span><span class="sxs-lookup"><span data-stu-id="d6fbc-114">Procedure description</span></span>|  
    |---------------------|---------------------------|  
    |<span data-ttu-id="d6fbc-115">Para exportar POVocabulary 1.0 y 1.1 mediante el Asistente para implementar el motor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="d6fbc-115">To export POVocabulary 1.0 and 1.1 by using the Business Rules Engine Deployment Wizard</span></span>|<span data-ttu-id="d6fbc-116">Proporciona instrucciones paso a paso para exportar las versiones 1.0 y 1.1 de la **POVocabulary** archivos vocabulario XML utilizando el Asistente para implementación de motor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-116">Provides step-by-step instructions for exporting versions 1.0 and 1.1 of the **POVocabulary** vocabulary to XML files by using the Business Rules Engine Deployment Wizard.</span></span>|  
    |<span data-ttu-id="d6fbc-117">Para exportar ProcessPurchaseOrder 1.3 mediante el Asistente para implementar el motor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="d6fbc-117">To export ProcessPurchaseOrder 1.3 by using the Business Rules Engine Deployment Wizard</span></span>|<span data-ttu-id="d6fbc-118">Proporciona instrucciones paso a paso para exportar la versión 1.3 de la **ProcessPurchaseOrder** directiva a un archivo XML utilizando el Asistente para implementación de motor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-118">Provides step-by-step instructions for exporting version 1.3 of the **ProcessPurchaseOrder** policy to an XML file by using the Business Rules Engine Deployment Wizard.</span></span>|  
    |<span data-ttu-id="d6fbc-119">Para eliminar ProcessPurchaseOrder y POVocabulary</span><span class="sxs-lookup"><span data-stu-id="d6fbc-119">To delete ProcessPurchaseOrder and POVocabulary</span></span>|<span data-ttu-id="d6fbc-120">Proporciona instrucciones paso a paso para eliminar la **ProcessPurchaseOrder** directiva y **POVocabulary** vocabulario importando el archivo XML de archivos para que pueda probar para volver a crearlos.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-120">Provides step-by-step instructions for deleting the **ProcessPurchaseOrder** policy and **POVocabulary** vocabulary so that you can test importing the XML files to re-create them.</span></span>|  
    |<span data-ttu-id="d6fbc-121">Para importar desde XML a fin de volver a crear POVocabulary 1.0 y 1.1</span><span class="sxs-lookup"><span data-stu-id="d6fbc-121">To import from XML to re-create POVocabulary 1.0 and 1.1</span></span>|<span data-ttu-id="d6fbc-122">Proporciona instrucciones paso a paso para importar el archivo XML de vocabulario que creó en el primer procedimiento para volver a crear la **POVocabulary** vocabulario.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-122">Provides step-by-step instructions for importing the vocabulary XML file you created in the first procedure to re-create the **POVocabulary** vocabulary.</span></span>|  
    |<span data-ttu-id="d6fbc-123">Para comprobar que se han vuelto a crear POVocabulary 1.0 y 1.1</span><span class="sxs-lookup"><span data-stu-id="d6fbc-123">To verify that POVocabulary 1.0 and 1.1 are re-created</span></span>|<span data-ttu-id="d6fbc-124">Proporciona instrucciones paso a paso para usar el Compositor de reglas de negocio para comprobar que las versiones 1.0 y 1.1 de **POVocabulary** se vuelven a crear.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-124">Provides step-by-step instructions for using the Business Rule Composer to verify that versions 1.0 and 1.1 of **POVocabulary** are re-created.</span></span>|  
    |<span data-ttu-id="d6fbc-125">Para importar desde XML a fin de volver a crear ProcessPurchaseOrder 1.3</span><span class="sxs-lookup"><span data-stu-id="d6fbc-125">To import from XML to re-create ProcessPurchaseOrder 1.3</span></span>|<span data-ttu-id="d6fbc-126">Proporciona instrucciones paso a paso para importar el archivo XML de directiva que creó en el segundo procedimiento para volver a crear la versión 1.3 de la **ProcessPurchaseOrder** directiva.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-126">Provides step-by-step instructions for importing the policy XML file you created in the second procedure to re-create version 1.3 of the **ProcessPurchaseOrder** policy.</span></span>|  
    |<span data-ttu-id="d6fbc-127">Para comprobar que se ha vuelto a crear ProcessPurchaseOrder 1.3</span><span class="sxs-lookup"><span data-stu-id="d6fbc-127">To verify that ProcessPurchaseOrder 1.3 is re-created</span></span>|<span data-ttu-id="d6fbc-128">Proporciona instrucciones paso a paso para usar el Compositor de reglas de negocio para comprobar que la versión 1.3 de la **ProcessPurchaseOrder** se vuelve a crear la directiva.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-128">Provides step-by-step instructions for using the Business Rule Composer to verify that version 1.3 of the **ProcessPurchaseOrder** policy is re-created.</span></span>|  
  
2.  <span data-ttu-id="d6fbc-129">El segundo tutorial contiene procedimientos para implementar la **ProcessPurchaseOrder** directiva mediante el uso de un archivo XML exportado desde la consola de administración de BizTalk Server la siguiente tabla describen los procedimientos de este tutorial.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-129">The second walkthrough contains procedures for deploying the **ProcessPurchaseOrder** policy by using an XML file exported from the BizTalk Server Administration console The following table describes the procedures in this walkthrough.</span></span>  
  
    |<span data-ttu-id="d6fbc-130">Título del procedimiento</span><span class="sxs-lookup"><span data-stu-id="d6fbc-130">Procedure title</span></span>|<span data-ttu-id="d6fbc-131">Descripción del procedimiento</span><span class="sxs-lookup"><span data-stu-id="d6fbc-131">Procedure description</span></span>|  
    |---------------------|---------------------------|  
    |<span data-ttu-id="d6fbc-132">Para exportar la directiva ProcessPurchaseOrder 1.3 y el vocabulario POVocabulary a un archivo XML</span><span class="sxs-lookup"><span data-stu-id="d6fbc-132">To export the ProcessPurchaseOrder 1.3 policy and the POVocabulary vocabulary to an XML file</span></span>|<span data-ttu-id="d6fbc-133">Proporciona instrucciones paso a paso para usar la consola de administración de BizTalk Server para exportar el **ProcessPurchaseOrder** directiva y la **POVocabulary** vocabulario a un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-133">Provides step-by-step instructions for using the BizTalk Server Administration console to export the **ProcessPurchaseOrder** policy and the **POVocabulary** vocabulary to an XML file.</span></span>|  
    |<span data-ttu-id="d6fbc-134">Para eliminar la directiva ProcessPurchaseOrder</span><span class="sxs-lookup"><span data-stu-id="d6fbc-134">To delete the ProcessPurchaseOrder policy</span></span>|<span data-ttu-id="d6fbc-135">Proporciona instrucciones paso a paso para eliminar la **ProcessPurchaseOrder** directiva desde **RuleTestApp** y la base de datos de motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-135">Provides step-by-step instructions for deleting the **ProcessPurchaseOrder** policy from **RuleTestApp** and the rule engine database.</span></span>|  
    |<span data-ttu-id="d6fbc-136">Para importar el archivo XML a fin de volver a crear la directiva ProcessPurchaseOrder</span><span class="sxs-lookup"><span data-stu-id="d6fbc-136">To import the XML file to re-create the ProcessPurchaseOrder policy</span></span>|<span data-ttu-id="d6fbc-137">Proporciona instrucciones paso a paso para importar el archivo XML exportado en el primer procedimiento para volver a crear la **ProcessPurchaseOrder** directiva.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-137">Provides step-by-step instructions for importing the XML file you exported in the first procedure to re-create the **ProcessPurchaseOrder** policy.</span></span>|  
    |<span data-ttu-id="d6fbc-138">Para agregar la directiva ProcessPurchaseOrder a la aplicación RuleTestApp </span><span class="sxs-lookup"><span data-stu-id="d6fbc-138">To add the ProcessPurchaseOrder policy to the RuleTestApp application</span></span>|<span data-ttu-id="d6fbc-139">Proporciona instrucciones paso a paso para agregar la **ProcessPurchaseOrder** directiva a la **RuleTestApp** aplicación.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-139">Provides step-by-step instructions for adding the **ProcessPurchaseOrder** policy to the **RuleTestApp** application.</span></span>|  
  
3.  <span data-ttu-id="d6fbc-140">El tercer tutorial contiene procedimientos para implementar la **ProcessPurchaseOrder** directiva mediante el uso de un archivo MSI exportado desde la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-140">The third walkthrough contains procedures for deploying the **ProcessPurchaseOrder** policy by using an MSI file exported from the BizTalk Server Administration console.</span></span> <span data-ttu-id="d6fbc-141">En la tabla siguiente se describen los procedimientos de este tutorial.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-141">The following table describes the procedures in this walkthrough.</span></span>  
  
    |<span data-ttu-id="d6fbc-142">Título del procedimiento</span><span class="sxs-lookup"><span data-stu-id="d6fbc-142">Procedure title</span></span>|<span data-ttu-id="d6fbc-143">El procedimiento contiene instrucciones paso a paso para</span><span class="sxs-lookup"><span data-stu-id="d6fbc-143">Procedure has step-by-step instructions for</span></span>|  
    |---------------------|---------------------------------------------------|  
    |<span data-ttu-id="d6fbc-144">Para exportar la aplicación RuleTestApp a un archivo MSI</span><span class="sxs-lookup"><span data-stu-id="d6fbc-144">To export the RuleTestApp application to an MSI file</span></span>|<span data-ttu-id="d6fbc-145">Proporciona instrucciones paso a paso para exportar el **RuleTestApp** aplicación a un archivo MSI, que se usará posteriormente para volver a crear la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-145">Provides step-by-step instructions for exporting the **RuleTestApp** application to an MSI file, which is used later to re-create the application.</span></span>|  
    |<span data-ttu-id="d6fbc-146">Para eliminar la aplicación RuleTestApp </span><span class="sxs-lookup"><span data-stu-id="d6fbc-146">To delete the RuleTestApp application</span></span>|<span data-ttu-id="d6fbc-147">Proporciona instrucciones paso a paso para eliminar la **RuleTestApp** aplicación para que pueda probar volver a crear la aplicación mediante el archivo MSI.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-147">Provides step-by-step instructions for deleting the **RuleTestApp** application so that you can test re-creating the application by using the MSI file.</span></span>|  
    |<span data-ttu-id="d6fbc-148">Para comprobar que la directiva ProcessPurchaseOrder y el vocabulario POVocabulary se han eliminado</span><span class="sxs-lookup"><span data-stu-id="d6fbc-148">To verify that the ProcessPurchaseOrder policy and POVocabulary vocabulary are deleted</span></span>|<span data-ttu-id="d6fbc-149">Proporciona instrucciones paso a paso para usar el Compositor de reglas de negocio para comprobar que la **ProcessPurchaseOrder** directiva y el vocabulario POVocabulary se eliminan.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-149">Provides step-by-step instructions for using the Business Rule Composer to verify that the **ProcessPurchaseOrder** policy and POVocabulary vocabulary are deleted.</span></span>|  
    |<span data-ttu-id="d6fbc-150">Para importar el archivo MSI a fin de volver a crear la aplicación RuleTestApp </span><span class="sxs-lookup"><span data-stu-id="d6fbc-150">To import the MSI file to re-create the RuleTestApp application</span></span>|<span data-ttu-id="d6fbc-151">Proporciona instrucciones paso a paso para usar la consola de administración de BizTalk Server para importar el archivo MSI para volver a crear la **RuleTestApp** aplicación.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-151">Provides step-by-step instructions for using the BizTalk Server Administration console to import the MSI file to re-create the **RuleTestApp** application.</span></span>|  
    |<span data-ttu-id="d6fbc-152">Para comprobar que la directiva ProcessPurchaseOrder se ha agregado a RuleTestApp </span><span class="sxs-lookup"><span data-stu-id="d6fbc-152">To verify that the ProcessPurchaseOrder policy is added to RuleTestApp</span></span>|<span data-ttu-id="d6fbc-153">Proporciona instrucciones paso a paso para usar la consola de administración de BizTalk Server para comprobar que la **ProcessPurchaseOrder** directiva se agrega a la **RuleTestApp** aplicación.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-153">Provides step-by-step instructions for using the BizTalk Server Administration console to verify that the **ProcessPurchaseOrder** policy is added to the **RuleTestApp** application.</span></span>|  
    |<span data-ttu-id="d6fbc-154">Para comprobar que la directiva ProcessPurchaseOrder y el vocabulario POVocabulary se han vuelto a crear</span><span class="sxs-lookup"><span data-stu-id="d6fbc-154">To verify that the ProcessPurchaseOrder policy and POVocabulary vocabulary are re-created</span></span>|<span data-ttu-id="d6fbc-155">Proporciona instrucciones paso a paso para usar el Compositor de reglas de negocio para comprobar que la **ProcessPurchaseOrder** directiva y **POVocabulary** vocabulario se vuelven a crear.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-155">Provides step-by-step instructions for using the Business Rule Composer to verify that the **ProcessPurchaseOrder** policy and **POVocabulary** vocabulary are re-created.</span></span>|  
    |<span data-ttu-id="d6fbc-156">Para probar la solución</span><span class="sxs-lookup"><span data-stu-id="d6fbc-156">To test the solution</span></span>|<span data-ttu-id="d6fbc-157">Proporciona instrucciones paso a paso para probar la solución.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-157">Provides step-by-step instructions for testing the solution.</span></span>|  
  
## <a name="procedures-for-deploying-the-processpurchaseorder-policy-by-using-the-business-rules-engine-deployment-wizard"></a><span data-ttu-id="d6fbc-158">Procedimientos para implementar la directiva ProcessPurchaseOrder mediante el Asistente para implementación de motor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="d6fbc-158">Procedures for Deploying the ProcessPurchaseOrder Policy by Using the Business Rules Engine Deployment Wizard</span></span>  
  
#### <a name="to-export-povocabulary-10-and-11-by-using-the-business-rules-engine-deployment-wizard"></a><span data-ttu-id="d6fbc-159">Para exportar POVocabulary 1.0 y 1.1 mediante el Asistente para implementar el motor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="d6fbc-159">To export POVocabulary 1.0 and 1.1 by using the Business Rules Engine Deployment Wizard</span></span>  
  
1.  <span data-ttu-id="d6fbc-160">En el **iniciar** menú Abrir **Asistente para implementación de motor de reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-160">On the **Start** menu, open **Business Rules Engine Deployment Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d6fbc-161">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-161">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="d6fbc-162">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-162">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="d6fbc-163">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-163">Click **Next**.</span></span>  
  
3.  <span data-ttu-id="d6fbc-164">En el **tarea de implementación** página, seleccione **Exportar directiva o vocabulario a archivo de base de datos**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-164">On the **Deployment Task** page, select **Export Policy/Vocabulary to file from database**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="d6fbc-165">En el **directiva Store** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-165">On the **Policy Store** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="d6fbc-166">En el **Exportar directiva o vocabulario** página, haga clic en **vocabulario**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-166">On the **Export Policy/Vocabulary** page, click **Vocabulary**.</span></span>  
  
6.  <span data-ttu-id="d6fbc-167">Seleccione **POVocabulary.1.0** en la lista desplegable para **directiva o vocabulario**, escriba o busque y especifique el nombre de archivo de salida XML como **C:\BRE-walkthroughs\POVocabulary10.xml**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-167">Select **POVocabulary.1.0** from the drop-down list for **Policy/Vocabulary**, type or browse to specify the XML output file name as **C:\BRE-walkthroughs\POVocabulary10.xml**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="d6fbc-168">En el **listo** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-168">On the **Ready** page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="d6fbc-169">En el **Exportando directiva o vocabulario** página, haga clic en **siguiente.**</span><span class="sxs-lookup"><span data-stu-id="d6fbc-169">On the **Exporting Policy/Vocabulary** page, click **Next.**</span></span>  
  
9. <span data-ttu-id="d6fbc-170">Seleccione **vuelva a ejecutar este asistente**y, a continuación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-170">Select **Run this wizard again**, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="d6fbc-171">Dado que seleccionó **vuelva a ejecutar este asistente**, la primera pantalla del asistente aparece de nuevo.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-171">Because you selected **Run this wizard again**, the first screen of the wizard appears again.</span></span>  
  
10. <span data-ttu-id="d6fbc-172">Repita los pasos 2 a 6.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-172">Repeat steps 2-6.</span></span>  
  
11. <span data-ttu-id="d6fbc-173">Seleccione **POVocabulary.1.1** en la lista desplegable para **directiva o vocabulario**, escriba o busque y especifique el nombre de archivo de salida XML como **C:\BRE-walkthroughs\POVocabulary11.xml**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-173">Select **POVocabulary.1.1** from the drop-down list for **Policy/Vocabulary**, type or browse to specify the XML output file name as **C:\BRE-walkthroughs\POVocabulary11.xml**, and then click **Next**.</span></span>  
  
12. <span data-ttu-id="d6fbc-174">Repita los pasos 8 y 9.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-174">Repeat steps 8 and 9.</span></span>  
  
13. <span data-ttu-id="d6fbc-175">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-175">Click **Finish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d6fbc-176">Debe exportar las versiones 1.0 y 1.1 de **POVocabulary** porque **ProcessPurchaseOrder** 1.3 depende de ambas versiones de **POVocabulary**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-176">You need to export both version 1.0 and version 1.1 of **POVocabulary** because **ProcessPurchaseOrder** 1.3 depends on both versions of **POVocabulary**.</span></span> <span data-ttu-id="d6fbc-177">El **número máximo de elementos permitidos** se utiliza la definición de la versión 1.1 del vocabulario.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-177">The **Maximum number of items allowed** definition is used from version 1.1 of the vocabulary.</span></span> <span data-ttu-id="d6fbc-178">El **cantidad solicitada** y **estado de la solicitud** se usan las definiciones de la versión 1.0.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-178">The **Requested Quantity** and **Request Status** definitions are used from version 1.0.</span></span>  
  
#### <a name="to-export-processpurchaseorder-13-by-using-the-business-rule-engine-deployment-wizard"></a><span data-ttu-id="d6fbc-179">Para exportar ProcessPurchaseOrder 1.3 mediante el Asistente para implementación de motor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="d6fbc-179">To export ProcessPurchaseOrder 1.3 by using the Business Rule Engine Deployment Wizard</span></span>  
  
1.  <span data-ttu-id="d6fbc-180">En el **iniciar** menú Abrir **Asistente para implementación de motor de reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-180">On the **Start** menu, open **Business Rules Engine Deployment Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d6fbc-181">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-181">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="d6fbc-182">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-182">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="d6fbc-183">En el **éste es el Asistente para la implementación del motor de reglas** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-183">On the **Welcome to the Rules Engine Deployment Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="d6fbc-184">Seleccione **Exportar directiva o vocabulario a archivo de base de datos**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-184">Select **Export Policy/Vocabulary to file from database**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="d6fbc-185">En el **directiva Store** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-185">On the **Policy Store** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="d6fbc-186">Compruebe que la **directiva** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-186">Verify that the **Policy** option is selected.</span></span>  
  
6.  <span data-ttu-id="d6fbc-187">Seleccione **ProcessPurchaseOrder.1.3** en la lista desplegable para **directiva o vocabulario**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-187">Select **ProcessPurchaseOrder.1.3** from the drop-down list for **Policy/Vocabulary**.</span></span>  
  
7.  <span data-ttu-id="d6fbc-188">Escriba o busque **C:\BRE-walkthroughs\ProcessPOPolicy13.xml** como el nombre de archivo de salida XML.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-188">Type or browse to specify **C:\BRE-walkthroughs\ProcessPOPolicy13.xml** as the XML output file name.</span></span>  
  
8.  <span data-ttu-id="d6fbc-189">Haga clic en **siguiente** tres veces al y, a continuación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-189">Click **Next** thrice, and then click **Finish**.</span></span>  
  
#### <a name="to-delete-processpurchaseorder-and-povocabulary"></a><span data-ttu-id="d6fbc-190">Para eliminar ProcessPurchaseOrder y POVocabulary</span><span class="sxs-lookup"><span data-stu-id="d6fbc-190">To delete ProcessPurchaseOrder and POVocabulary</span></span>  
  
1.  <span data-ttu-id="d6fbc-191">En el **iniciar** menú Abrir **compositor**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-191">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="d6fbc-192">Si tiene ya, presione F5 o haga clic en el Compositor de reglas de negocio **recarga** en el **archivo** menú para actualizarlo.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-192">If you have Business Rule Composer already open, press F5 or click **Reload** on the **File** menu to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d6fbc-193">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-193">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="d6fbc-194">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-194">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="d6fbc-195">En la ventana Explorador de directivas, expanda **directivas**, expanda **ProcessPurchaseOrder**, haga clic en **versión 1.0**y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-195">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.0**, and then click **Delete**.</span></span> <span data-ttu-id="d6fbc-196">Si **eliminar** está deshabilitado, haga clic en **versión 1.0**y, a continuación, haga clic en **Undeploy**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-196">If **Delete** is disabled, right-click **Version 1.0**, and then click **Undeploy**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d6fbc-197">Las versiones de directivas implementadas no se pueden eliminar.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-197">The deployed policy versions cannot be deleted.</span></span> <span data-ttu-id="d6fbc-198">Es preciso anular la implementación de una directiva para poder eliminar una versión de esa directiva.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-198">You must undeploy a policy before deleting a policy version.</span></span>  
  
3.  <span data-ttu-id="d6fbc-199">Haga clic en **Sí** en el cuadro de mensaje de confirmación.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-199">Click **Yes** in the confirmation message box.</span></span>  
  
4.  <span data-ttu-id="d6fbc-200">Repita los pasos 2 y 3 para eliminar **versión 1.1**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-200">Repeat steps 2 and 3 to delete **Version 1.1**.</span></span>  
  
5.  <span data-ttu-id="d6fbc-201">Repita los pasos 2 y 3 para eliminar **versión 1.2**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-201">Repeat steps 2 and 3 to delete **Version 1.2**.</span></span>  
  
6.  <span data-ttu-id="d6fbc-202">Haga clic en **versión 1.3 implementada**y, a continuación, haga clic en **Undeploy**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-202">Right-click **Version 1.3 - Deployed**, and then click **Undeploy**.</span></span> <span data-ttu-id="d6fbc-203">Si el **Undeploy** opción está deshabilitada, omita este paso.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-203">If the **Undeploy** option is disabled, ignore this step.</span></span>  
  
7.  <span data-ttu-id="d6fbc-204">En la ventana Explorador de hechos, expanda **vocabularios**, haga clic en **POVocabulary**y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-204">In the Facts Explorer window, expand **Vocabularies**, right-click **POVocabulary**, and then click **Delete**.</span></span>  
  
#### <a name="to-import-from-xml-to-re-create-povocabulary-10-and-11"></a><span data-ttu-id="d6fbc-205">Para importar desde XML a fin de volver a crear POVocabulary 1.0 y 1.1</span><span class="sxs-lookup"><span data-stu-id="d6fbc-205">To import from XML to re-create POVocabulary 1.0 and 1.1</span></span>  
  
1.  <span data-ttu-id="d6fbc-206">En el **iniciar** menú Abrir **Asistente para implementación de motor de reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-206">On the **Start** menu, open **Business Rules Engine Deployment Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d6fbc-207">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-207">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="d6fbc-208">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-208">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="d6fbc-209">En el **éste es el Asistente para la implementación del motor de reglas**, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-209">On the **Welcome to the Rules Engine Deployment Wizard**, click **Next**.</span></span>  
  
3.  <span data-ttu-id="d6fbc-210">En el **tarea de implementación** página, seleccione **importar y publicar la directiva o vocabulario a la base de datos desde un archivo**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-210">On the **Deployment Task** page, select **Import and publish Policy/Vocabulary to database from file**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="d6fbc-211">En el **directiva Store** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-211">On the **Policy Store** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="d6fbc-212">Busque y seleccione el **POVocabulary10.xml** archivo que creó en el primer procedimiento.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-212">Browse and select the **POVocabulary10.xml** file you created in the first procedure.</span></span>  
  
6.  <span data-ttu-id="d6fbc-213">Haga clic en **abierto** o haga doble clic en **POVocabulary10.xml**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-213">Click **Open** or double-click **POVocabulary10.xml**.</span></span>  
  
7.  <span data-ttu-id="d6fbc-214">Haga clic en **siguiente** en el Asistente para implementación de motor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-214">Click **Next** in the Business Rules Engine Deployment Wizard.</span></span>  
  
8.  <span data-ttu-id="d6fbc-215">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-215">Click **Next**.</span></span>  
  
9. <span data-ttu-id="d6fbc-216">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-216">Click **Next**.</span></span>  
  
10. <span data-ttu-id="d6fbc-217">Seleccione **vuelva a ejecutar este asistente**y, a continuación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-217">Select **Run this wizard again**, and then click **Finish**.</span></span>  
  
11. <span data-ttu-id="d6fbc-218">Repita los pasos del 2 al 9 para importar **POVocabulary11.xml**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-218">Repeat steps 2-9 to import **POVocabulary11.xml**.</span></span>  
  
12. <span data-ttu-id="d6fbc-219">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-219">Click **Finish**.</span></span>  
  
#### <a name="to-verify-that-povocabulary-10-and-11-are-re-created"></a><span data-ttu-id="d6fbc-220">Para comprobar que se han vuelto a crear POVocabulary 1.0 y 1.1</span><span class="sxs-lookup"><span data-stu-id="d6fbc-220">To verify that POVocabulary 1.0 and 1.1 are re-created</span></span>  
  
1.  <span data-ttu-id="d6fbc-221">En el **iniciar** menú Abrir **compositor**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-221">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="d6fbc-222">Si tiene ya está abierto, presione F5 o haga clic en **recarga** en el **archivo** menú para actualizarlo.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-222">If you have it already open, press F5 or click **Reload** on the **File** menu to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d6fbc-223">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-223">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="d6fbc-224">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-224">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="d6fbc-225">En la ventana Explorador de hechos, haga clic en el **vocabularios** ficha.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-225">In the Facts Explorer window, click the **Vocabularies** tab.</span></span>  
  
3.  <span data-ttu-id="d6fbc-226">Expanda **vocabularios**, y debería ver **POVocabulary**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-226">Expand **Vocabularies**, and you should see **POVocabulary**.</span></span>  
  
4.  <span data-ttu-id="d6fbc-227">Expanda **POVocabulary**, y debería ver **versión 1.0** y **versión 1.1**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-227">Expand **POVocabulary**, and you should see **Version 1.0** and **Version 1.1**.</span></span>  
  
#### <a name="to-import-from-xml-to-re-create-processpurchaseorder-13"></a><span data-ttu-id="d6fbc-228">Para importar desde XML a fin de volver a crear ProcessPurchaseOrder 1.3</span><span class="sxs-lookup"><span data-stu-id="d6fbc-228">To import from XML to re-create ProcessPurchaseOrder 1.3</span></span>  
  
1.  <span data-ttu-id="d6fbc-229">En el **iniciar** menú Abrir **Asistente para implementación de motor de reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-229">On the **Start** menu, open **Business Rules Engine Deployment Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d6fbc-230">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-230">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="d6fbc-231">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-231">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="d6fbc-232">En el **éste es el Asistente para la implementación del motor de reglas**, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-232">On the **Welcome to the Rules Engine Deployment Wizard**, click **Next**.</span></span>  
  
3.  <span data-ttu-id="d6fbc-233">En el **tarea de implementación** página, seleccione **importar y publicar una directiva o vocabulario a la base de datos desde archivopara base de datos de archivo**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-233">On the **Deployment Task** page, select **Import and publish Policy/Vocabulary to database from fileto database from file**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="d6fbc-234">En el **directiva Store** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-234">On the **Policy Store** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="d6fbc-235">Busque y seleccione el **ProcessPOPolicy13.xml** archivo que creó anteriormente en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-235">Browse and select the **ProcessPOPolicy13.xml** file you created earlier in this walkthrough.</span></span>  
  
6.  <span data-ttu-id="d6fbc-236">Haga clic en **abierto** o haga doble clic en **ProcessPOPolicy13.xml**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-236">Click **Open** or double-click **ProcessPOPolicy13.xml**.</span></span>  
  
7.  <span data-ttu-id="d6fbc-237">Haga clic en **siguiente** en el Asistente para implementación de motor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-237">Click **Next** in the Business Rules Engine Deployment Wizard.</span></span>  
  
8.  <span data-ttu-id="d6fbc-238">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-238">Click **Next**.</span></span>  
  
9. <span data-ttu-id="d6fbc-239">Haga clic en **Siguiente**y, a continuación, en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-239">Click **Next**, and then click **Finish**.</span></span>  
  
#### <a name="to-verify-that-processpurchaseorder-13-is-re-created"></a><span data-ttu-id="d6fbc-240">Para comprobar que se ha vuelto a crear ProcessPurchaseOrder 1.3</span><span class="sxs-lookup"><span data-stu-id="d6fbc-240">To verify that ProcessPurchaseOrder 1.3 is re-created</span></span>  
  
1.  <span data-ttu-id="d6fbc-241">En el **iniciar** menú Abrir **compositor**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-241">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="d6fbc-242">Si tiene ya está abierto, presione F5 o haga clic en **recarga** en el **archivo** menú para actualizarlo.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-242">If you have it already open, press F5 or click **Reload** on the **File** menu to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d6fbc-243">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-243">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="d6fbc-244">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-244">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="d6fbc-245">En la ventana Explorador de directivas, expanda **directivas** y debería ver **ProcessPurchaseOrder**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-245">In the Policy Explorer window, expand **Policies** and you should see **ProcessPurchaseOrder**.</span></span>  
  
3.  <span data-ttu-id="d6fbc-246">Expanda **ProcessPurchaseOrder** y debería ver **versión 1.3 publicada**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-246">Expand **ProcessPurchaseOrder** and you should see **Version 1.3 - Published**.</span></span>  
  
## <a name="procedures-for-deploying-the-policy-by-using-an-xml-file-exported-from-the-biztalk-server-administration-console"></a><span data-ttu-id="d6fbc-247">Procedimientos para implementar la directiva mediante un archivo XML exportado desde la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="d6fbc-247">Procedures for Deploying the Policy by Using an XML file Exported from the BizTalk Server Administration Console</span></span>  
  
#### <a name="to-export-the-processpurchaseorder-13-policy-and-the-povocabulary-vocabulary-to-an-xml-file"></a><span data-ttu-id="d6fbc-248">Para exportar la directiva ProcessPurchaseOrder 1.3 y el vocabulario POVocabulary a un archivo XML</span><span class="sxs-lookup"><span data-stu-id="d6fbc-248">To export the ProcessPurchaseOrder 1.3 policy and the POVocabulary vocabulary to an XML file</span></span>  
  
1. <span data-ttu-id="d6fbc-249">En el **iniciar** menú Abrir [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6fbc-249">On the **Start** menu, open [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span> <span data-ttu-id="d6fbc-250">Si la herramienta ya está abierta, presione F5 para actualizarla.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-250">If you have the tool already open, press F5 to refresh it.</span></span>  
  
2. <span data-ttu-id="d6fbc-251">Expanda **raíz de consola**, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda **RuleTestApp** .</span><span class="sxs-lookup"><span data-stu-id="d6fbc-251">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, expand **Applications**, and then expand **RuleTestApp**.</span></span>  
  
3. <span data-ttu-id="d6fbc-252">Haga clic en **directivas** y asegúrese de que ve la directiva ProcessPurchaseOrder 1.3 de la lista.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-252">Click **Policies** and make sure that you see the ProcessPurchaseOrder 1.3 policy in the list.</span></span>  
  
4. <span data-ttu-id="d6fbc-253">Haga clic en **ProcessPurchaseOrder**y, a continuación, haga clic en **exportar**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-253">Right-click **ProcessPurchaseOrder**, and then click **Export**.</span></span>  
  
5. <span data-ttu-id="d6fbc-254">En el **exportar directivas** diálogo cuadro, asegúrese de que el **ProcessPurchaseOrder** directiva y la **POVocabulary** están seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-254">In the **Export Policies** dialog box, make sure the **ProcessPurchaseOrder** policy and the **POVocabulary** are selected.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d6fbc-255">Puede exportar todas las directivas en una aplicación en un archivo XML con el botón secundario **RuleTest** y, a continuación, haga clic en **exportar** en el **directivas** menú.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-255">You can export all the policies in an application to an XML file by right-clicking **RuleTest** and then clicking **Export** on the **Policies** menu.</span></span> <span data-ttu-id="d6fbc-256">De este modo, se exportan todas las directivas y el vocabulario usados por esta aplicación a un mismo archivo XML.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-256">This way you can export all the policies and vocabulary used by this application to a single XML file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d6fbc-257">Puede exportar todas las directivas en todas las aplicaciones en un archivo XML haciendo clic con el **aplicaciones** nodo y, a continuación, haga clic en **exportar** en el **directivas** menú.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-257">You can export all the policies in all the applications to an XML file by right-clicking the **Applications** node and then clicking **Export** on the **Policies** menu.</span></span> <span data-ttu-id="d6fbc-258">De este modo, se exportan todas las directivas y vocabularios usados en todas las aplicaciones a un mismo archivo XML.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-258">This way you can export all the policies and vocabularies used by all the applications into a single XML file.</span></span>  
  
6. <span data-ttu-id="d6fbc-259">Especifique un nombre de archivo XML de salida (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-259">Specify an output XML file name (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**), and then click **Ok**.</span></span>  
  
#### <a name="to-delete-the-processpurchaseorder-policy"></a><span data-ttu-id="d6fbc-260">Para eliminar la directiva ProcessPurchaseOrder</span><span class="sxs-lookup"><span data-stu-id="d6fbc-260">To delete the ProcessPurchaseOrder policy</span></span>  
  
1.  <span data-ttu-id="d6fbc-261">En administración de BizTalk Server, haga clic en **ProcessPurchaseOrder** en la lista y, a continuación, haga clic en **quitar**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-261">In BizTalk Server Administration, right-click **ProcessPurchaseOrder** in the list, and then click **Remove**.</span></span>  
  
2.  <span data-ttu-id="d6fbc-262">Haga clic en **Sí** en el **Quitar directiva** cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-262">Click **Yes** in the **Remove Policy** message box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d6fbc-263">Si la directiva está en estado implementado, no se puede quitar.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-263">If the policy is in the deployed state, it cannot be removed.</span></span> <span data-ttu-id="d6fbc-264">Haga clic en **ProcessPurchaseOrder**y, a continuación, haga clic en **Undeploy** para anular la implementación de la directiva.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-264">Right-click **ProcessPurchaseOrder**, and then click **Undeploy** to undeploy the policy.</span></span> <span data-ttu-id="d6fbc-265">El **quitar** elemento de menú está disponible cuando la directiva está implementada.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-265">The **Remove** menu item is available when the policy is undeployed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d6fbc-266">Los vocabularios en el que el **ProcessPurchaseOrder** directiva depende, en este caso **POVocabulary**, también se eliminan.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-266">The vocabularies on which the **ProcessPurchaseOrder** policy depends, in this case **POVocabulary**, are also deleted.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d6fbc-267">Cuando se quita una directiva de una aplicación, tanto la directiva como los vocabularios de los que depende se eliminan asimismo de la base de datos del motor de reglas, no sólo de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-267">When you remove a policy from an application, the policy and the vocabularies that it depends on are deleted from the rule engine database as well, not just from the application.</span></span>  
  
#### <a name="to-import-the-xml-file-to-re-create-the-processpurchaseorder-policy"></a><span data-ttu-id="d6fbc-268">Para importar el archivo XML a fin de volver a crear la directiva ProcessPurchaseOrder</span><span class="sxs-lookup"><span data-stu-id="d6fbc-268">To import the XML file to re-create the ProcessPurchaseOrder policy</span></span>  
  
1. <span data-ttu-id="d6fbc-269">En administración de BizTalk Server, expanda **raíz de consola**, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]y, a continuación, expanda **grupo de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-269">In BizTalk Server Administration, expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then expand **BizTalk Group**.</span></span>  
  
2. <span data-ttu-id="d6fbc-270">Haga clic en **aplicaciones**, apunte a **importación**y, a continuación, haga clic en **directivas**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-270">Right-click **Applications**, point to **Import**, and then click **Policies**.</span></span>  
  
3. <span data-ttu-id="d6fbc-271">Busque y haga doble clic en el archivo XML (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**) que creó en el primer procedimiento.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-271">Browse, and double-click the XML file (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**) that you created in the first procedure.</span></span>  
  
4. <span data-ttu-id="d6fbc-272">Expanda **\<todos los artefactos\>** en **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-272">Expand **\<All Artifacts\>** under **Applications**.</span></span>  
  
5. <span data-ttu-id="d6fbc-273">Haga clic en **directivas**, y debería ver la versión 1.3 de la **ProcessPurchaseOrder** directiva en la lista.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-273">Click **Policies**, and you should see version 1.3 of the **ProcessPurchaseOrder** policy in the list.</span></span>  
  
6. <span data-ttu-id="d6fbc-274">Presione F5 para actualizar la vista.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-274">Press F5 to refresh the view.</span></span> <span data-ttu-id="d6fbc-275">El **ProcessPurchaseOrder** directiva debe estar en el **no publicado** estado.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-275">The **ProcessPurchaseOrder** policy should be in the **Not Published** state.</span></span>  
  
#### <a name="to-add-the-processpurchaseorder-policy-to-the-ruletestapp-application"></a><span data-ttu-id="d6fbc-276">Para agregar la directiva ProcessPurchaseOrder a la aplicación RuleTestApp </span><span class="sxs-lookup"><span data-stu-id="d6fbc-276">To add the ProcessPurchaseOrder policy to the RuleTestApp application</span></span>  
  
1.  <span data-ttu-id="d6fbc-277">En administración de BizTalk Server, haga clic en **ProcessPurchaseOrder** directiva y, a continuación, haga clic en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-277">In BizTalk Server Administration, right-click **ProcessPurchaseOrder** policy, and then click **Publish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d6fbc-278">Sólo se pueden agregar a una aplicación de BizTalk las directivas publicadas.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-278">Only published policies can be added to a BizTalk application.</span></span>  
  
2.  <span data-ttu-id="d6fbc-279">En el **aplicaciones** nodo, expanda **RuleTestApp**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-279">In the **Applications** node, expand **RuleTestApp**.</span></span>  
  
3.  <span data-ttu-id="d6fbc-280">Haga clic en **directivas** en **RuleTestApp**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-280">Click **Policies** in **RuleTestApp**.</span></span>  
  
4.  <span data-ttu-id="d6fbc-281">Haga clic en la lista de la derecha, seleccione **agregar**y, a continuación, haga clic en **directiva**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-281">Right-click in the list on the right, point to **Add**, and then click **Policy**.</span></span>  
  
5.  <span data-ttu-id="d6fbc-282">Expanda el **ProcessPurchaseOrder** nodo, seleccione la casilla de verificación **versión 1.3 (publicada)** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-282">Expand the **ProcessPurchaseOrder** node, select the check box for **Version 1.3 (Published)**, and then click **OK**.</span></span> <span data-ttu-id="d6fbc-283">.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-283">.</span></span>  
  
6.  <span data-ttu-id="d6fbc-284">Haga clic en **ProcessPurchaseOrder**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-284">Right-click **ProcessPurchaseOrder**, and then click **Deploy**.</span></span> <span data-ttu-id="d6fbc-285">Si no ve **ProcessPurchaseOrder** en la lista, presione F5 para actualizar la vista.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-285">If you do not see **ProcessPurchaseOrder** in the list, press F5 to refresh the view.</span></span>  
  
7.  <span data-ttu-id="d6fbc-286">Haga clic en **Sí** en el cuadro de mensaje de confirmación.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-286">Click **Yes** in the confirmation message box.</span></span>  
  
## <a name="procedures-for-deploying-the-policy-by-using-an-msi-file"></a><span data-ttu-id="d6fbc-287">Procedimientos para implementar la directiva mediante un archivo MSI</span><span class="sxs-lookup"><span data-stu-id="d6fbc-287">Procedures for Deploying the Policy by Using an MSI File</span></span>  
  
#### <a name="to-export-the-ruletestapp-application-to-an-msi-file"></a><span data-ttu-id="d6fbc-288">Para exportar la aplicación RuleTestApp a un archivo MSI</span><span class="sxs-lookup"><span data-stu-id="d6fbc-288">To export the RuleTestApp application to an MSI file</span></span>  
  
1. <span data-ttu-id="d6fbc-289">En el **iniciar** menú Abrir **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-289">On the **Start** menu, open **BizTalk Server Administration**.</span></span> <span data-ttu-id="d6fbc-290">Si la herramienta ya está abierta, presione F5 para actualizarla.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-290">If you have the tool already open, press F5 to refresh it.</span></span>  
  
2. <span data-ttu-id="d6fbc-291">Expanda **raíz de consola**, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-291">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="d6fbc-292">Haga clic en **RuleTestApp**, apunte a **exportar**y, a continuación, haga clic en **archivo MSI**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-292">Right-click **RuleTestApp**, point to **Export**, and then click **MSI file**.</span></span>  
  
4. <span data-ttu-id="d6fbc-293">En el **éste es el Asistente para exportar archivos MSI** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-293">On the **Welcome to the Export MSI File Wizard** page, click **Next**.</span></span>  
  
5. <span data-ttu-id="d6fbc-294">En el **seleccionar recursos** , revise todas las opciones predeterminadas y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-294">On the **Select Resources** page, review all the default options, and then click **Next**.</span></span>  
  
6. <span data-ttu-id="d6fbc-295">En el **especificar Hosts de ISS** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-295">On the **Specify IIS Hosts** page, click **Next**.</span></span>  
  
7. <span data-ttu-id="d6fbc-296">En el **dependencias** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-296">On the **Dependencies** page, click **Next**.</span></span>  
  
8. <span data-ttu-id="d6fbc-297">En el **destino** , especifique el directorio y el nombre del archivo msi **C:\BRE-Walkthroughs\RuleTestApp.msi**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-297">On the **Destination** page, specify the directory and name for the MSI as **C:\BRE-Walkthroughs\RuleTestApp.msi**.</span></span>  
  
9. <span data-ttu-id="d6fbc-298">Haga clic en **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-298">Click **Export**.</span></span>  
  
10. <span data-ttu-id="d6fbc-299">En el **resumen** página, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-299">On the **Summary** page, click **Finish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d6fbc-300">Al exportar la aplicación RuleTestApp, las directivas y los vocabularios usados en esa aplicación también se exportan al archivo MSI.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-300">When you export the RuleTestApp application, the policies and vocabularies used by the application are also exported in the MSI file.</span></span> <span data-ttu-id="d6fbc-301">Posteriormente, cuando importe el archivo MSI, se volverán a crear el vocabulario, la directiva y la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-301">Later, when you import the MSI file, the vocabulary, policy, and application are all re-created.</span></span>  
  
#### <a name="to-delete-the-ruletestapp-application"></a><span data-ttu-id="d6fbc-302">Para eliminar la aplicación RuleTestApp </span><span class="sxs-lookup"><span data-stu-id="d6fbc-302">To delete the RuleTestApp application</span></span>  
  
1.  <span data-ttu-id="d6fbc-303">En administración de BizTalk Server, haga clic en **RuleTestApp**y compruebe si el **eliminar** menú está habilitado o deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-303">In BizTalk Server Administration, right-click **RuleTestApp**, and check if the **Delete** menu is enabled or disabled.</span></span>  
  
2.  <span data-ttu-id="d6fbc-304">Si **eliminar** está deshabilitado, haga clic en **RuleTestApp**, haga clic en **detener**, seleccione **detención completa: finalizar instancia**y, a continuación, haga clic en  **Detener**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-304">If **Delete** is disabled, right-click **RuleTestApp**, click **Stop**, select **Full Stop - Terminate Instance**, and then click **Stop**.</span></span>  
  
3.  <span data-ttu-id="d6fbc-305">Haga clic en **RuleTestApp**y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-305">Right-click **RuleTestApp**, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="d6fbc-306">Haga clic en **Sí** para confirmar la eliminación.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-306">Click **Yes** to confirm deletion.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d6fbc-307">Cuando se elimina una aplicación, todas las directivas de la aplicación y los vocabularios dependientes se eliminan asimismo de la base de datos del motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-307">When you delete an application, all the policies in the application and dependent vocabularies are deleted from the rule engine database as well.</span></span>  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-and-povocabulary-vocabulary-are-deleted"></a><span data-ttu-id="d6fbc-308">Para comprobar que la directiva ProcessPurchaseOrder y el vocabulario POVocabulary se han eliminado</span><span class="sxs-lookup"><span data-stu-id="d6fbc-308">To verify that the ProcessPurchaseOrder policy and POVocabulary vocabulary are deleted</span></span>  
  
1.  <span data-ttu-id="d6fbc-309">En el **iniciar** menú Abrir **compositor**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-309">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="d6fbc-310">Si tiene compositor ya abierto, presione F5 para actualizarlo.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-310">If you have Business Rule Composer already open, press F5 to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d6fbc-311">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-311">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="d6fbc-312">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-312">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="d6fbc-313">En la ventana Explorador de directivas, expanda **directivas**y asegúrese de que no existe la directiva ProcessPurchaseOrder.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-313">In the Policy Explorer window, expand **Policies**, and make sure that the ProcessPurchaseOrder policy does not exist.</span></span>  
  
3.  <span data-ttu-id="d6fbc-314">En la ventana Explorador de hechos, expanda **vocabularios**y asegúrese de que no existe POVocabulary.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-314">In the Facts Explorer window, expand **Vocabularies**, and make sure that POVocabulary does not exist.</span></span>  
  
#### <a name="to-import-the-msi-file-to-re-create-the-ruletestapp-application"></a><span data-ttu-id="d6fbc-315">Para importar el archivo MSI a fin de volver a crear la aplicación RuleTestApp </span><span class="sxs-lookup"><span data-stu-id="d6fbc-315">To import the MSI file to re-create the RuleTestApp application</span></span>  
  
1. <span data-ttu-id="d6fbc-316">En el **iniciar** menú Abrir **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-316">On the **Start** menu, open **BizTalk Server Administration**.</span></span> <span data-ttu-id="d6fbc-317">Si la consola de administración de BizTalk Server ya está abierta, presione F5 para actualizarla.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-317">If you have the BizTalk Server Administration console already open, press F5 to refresh it.</span></span>  
  
2. <span data-ttu-id="d6fbc-318">Expanda **raíz de consola**, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]y, a continuación, expanda **grupo de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-318">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then expand **BizTalk Group**.</span></span>  
  
3. <span data-ttu-id="d6fbc-319">Haga clic en **aplicaciones**, apunte a **importación**y, a continuación, haga clic en **archivo MSI**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-319">Right-click **Applications**, point to **Import**, and then click **MSI file**.</span></span>  
  
4. <span data-ttu-id="d6fbc-320">En el **el Asistente para importar** página, busque y seleccione el archivo MSI (RuleTestApp.msi) que exportó anteriormente para el **archivo MSI para importar** configuración.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-320">On the **Welcome to the Import Wizard** page, browse and select the MSI file (RuleTestApp.msi) you exported earlier for the **MSI file to import** setting.</span></span>  
  
5. <span data-ttu-id="d6fbc-321">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-321">Click **Next**.</span></span>  
  
6. <span data-ttu-id="d6fbc-322">En el **configuración de la aplicación** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-322">On the **Application Settings** page, click **Next**.</span></span>  
  
7. <span data-ttu-id="d6fbc-323">En el **configuración del entorno de destino de aplicación** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-323">On the **Application Target Environment Settings** page, click **Next**.</span></span>  
  
8. <span data-ttu-id="d6fbc-324">En el **resumen de importación** página, haga clic en **importación**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-324">On the **Import Summary** page, click **Import**.</span></span>  
  
9. <span data-ttu-id="d6fbc-325">En el **importación se realizó correctamente** página, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-325">On the **Import Succeeded** page, click **Finish**.</span></span> <span data-ttu-id="d6fbc-326">Debería ver que el **RuleTestApp** aplicación se crea en **aplicaciones** en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-326">You should see that the **RuleTestApp** application is created under **Applications** in the BizTalk Server Administration console.</span></span>  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-is-added-to-ruletestapp"></a><span data-ttu-id="d6fbc-327">Para comprobar que la directiva ProcessPurchaseOrder se ha agregado a RuleTestApp </span><span class="sxs-lookup"><span data-stu-id="d6fbc-327">To verify that the ProcessPurchaseOrder policy is added to RuleTestApp</span></span>  
  
1.  <span data-ttu-id="d6fbc-328">Expanda **RuleTestApp** en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-328">Expand **RuleTestApp** in the BizTalk Server Administration console.</span></span>  
  
2.  <span data-ttu-id="d6fbc-329">Seleccione **directivas** y debería ver **ProcessPurchaseOrder** en la lista en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-329">Select **Policies** and you should see **ProcessPurchaseOrder** in the list in the right pane.</span></span>  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-and-povocabulary-vocabulary-are-re-created"></a><span data-ttu-id="d6fbc-330">Para comprobar que la directiva ProcessPurchaseOrder y el vocabulario POVocabulary se han vuelto a crear</span><span class="sxs-lookup"><span data-stu-id="d6fbc-330">To verify that the ProcessPurchaseOrder policy and POVocabulary vocabulary are re-created</span></span>  
  
1.  <span data-ttu-id="d6fbc-331">En el **iniciar** menú Abrir **compositor**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-331">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="d6fbc-332">Si ya está abierto, presione F5 para actualizarlo.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-332">If you have it already open, press F5 to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d6fbc-333">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-333">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="d6fbc-334">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-334">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="d6fbc-335">En la ventana Explorador de directivas, expanda **directivas**y asegúrese de que **ProcessPurchaseOrder** existe.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-335">In the Policy Explorer window, expand **Policies**, and make sure that **ProcessPurchaseOrder** exists.</span></span>  
  
3.  <span data-ttu-id="d6fbc-336">En la ventana Explorador de hechos, expanda **vocabularios**y asegúrese de que **POVocabulary** existe.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-336">In the Facts Explorer window, expand **Vocabularies**, and make sure that **POVocabulary** exists.</span></span>  
  
#### <a name="to-test-the-solution"></a><span data-ttu-id="d6fbc-337">Para probar la solución</span><span class="sxs-lookup"><span data-stu-id="d6fbc-337">To test the solution</span></span>  
  
1. <span data-ttu-id="d6fbc-338">En el **iniciar** menú Abrir **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-338">On the **Start** menu, open **BizTalk Server Administration**.</span></span> <span data-ttu-id="d6fbc-339">Si la consola de administración de BizTalk Server ya está abierta, presione F5 para actualizarla.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-339">If you have the BizTalk Server Administration console already open, press F5 to refresh it.</span></span>  
  
2. <span data-ttu-id="d6fbc-340">Expanda **raíz de consola**, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-340">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="d6fbc-341">Haga clic en **RuleTestApp**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-341">Right-click **RuleTestApp**, and then click **Start**.</span></span>  
  
4. <span data-ttu-id="d6fbc-342">Haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-342">Click **Start**.</span></span>  
  
5. <span data-ttu-id="d6fbc-343">Copia **SamplePO.xml** que creó en [Tutorial: probar la directiva](../core/walkthrough-testing-the-policy.md) al directorio de entrada para la orquestación.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-343">Copy **SamplePO.xml** that you created in [Walkthrough: Testing the Policy](../core/walkthrough-testing-the-policy.md) to the input directory for the orchestration.</span></span>  
  
6. <span data-ttu-id="d6fbc-344">Debería ver un archivo de salida en el directorio de salida de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-344">You should see an output file in the output directory for the orchestration.</span></span> <span data-ttu-id="d6fbc-345">Abra el archivo XML de salida y observe que el valor de la **estado** campo se establece en **aprobado**.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-345">Open the output XML file and notice that the value of the **Status** field is set to **Approved**.</span></span>  
  
7. <span data-ttu-id="d6fbc-346">Repita los pasos 3 y 4 con **SamplePO2.xml**y tenga en cuenta que el valor de la **estado** campo en el documento de salida es igual que en el documento de entrada (**XYZ**).</span><span class="sxs-lookup"><span data-stu-id="d6fbc-346">Repeat steps 3 and 4 with **SamplePO2.xml**, and notice that the value of the **Status** field in the output document is the same as in the input document (**XYZ**).</span></span>  
  
## <a name="comments"></a><span data-ttu-id="d6fbc-347">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d6fbc-347">Comments</span></span>  
  
-   <span data-ttu-id="d6fbc-348">Es **muy importante** recordar que, cuando se quita una directiva desde una aplicación, no solo quita la asociación entre la aplicación y la directiva; eliminar también la directiva y su vocabulario asociado de la regla base de datos del motor.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-348">It is **very important** to remember that when you remove a policy from an application, you do not just remove the association between the application and the policy; you also delete the policy and its associated vocabulary from the rule engine database.</span></span>  
  
-   <span data-ttu-id="d6fbc-349">Al iniciar una aplicación, ésta implementa de manera predeterminada y automática todas las directivas.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-349">When you start an application, by default, it deploys the policies automatically.</span></span> <span data-ttu-id="d6fbc-350">De forma similar, al detener una aplicación y seleccionar **detención completa: finalizar instancias**, las directivas asociadas se anula automáticamente.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-350">Similarly, when you stop an application and select **Full Stop - Terminate Instances**, the associated policies are undeployed automatically.</span></span> <span data-ttu-id="d6fbc-351">Al seleccionar **detención parcial: suspender las instancias en ejecución**, las directivas asociadas no se anula automáticamente.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-351">When you select **Partial Stop - Suspend running instances**, the associated policies are not undeployed automatically.</span></span>  
  
-   <span data-ttu-id="d6fbc-352">Debe actualizar las vistas del Compositor de reglas de negocio y de la consola de administración de BizTalk Server para asegurarse de estar viendo la información más reciente antes de llevar a cabo cualquier operación.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-352">You should refresh the views in Business Rule Composer and BizTalk Server Administration console to make sure you are looking at the latest information before performing any operation.</span></span>  
  
-   <span data-ttu-id="d6fbc-353">Si crea una versión nueva de la directiva cuya versión anterior está asociada a una aplicación de BizTalk, debe agregar manualmente a la aplicación la nueva versión de la directiva.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-353">If you create a new version of the policy whose earlier version is associated with a BizTalk application, you should manually add the new version of the policy to the application.</span></span> <span data-ttu-id="d6fbc-354">No debe quitar la versión anterior de la directiva a no ser que desee eliminarla por completo de la base de datos del motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-354">You should not remove the old version of the policy unless you really want to delete it from the rule engine database.</span></span>  
  
-   <span data-ttu-id="d6fbc-355">Puede combinar dos o más archivos BRL (archivos XML de Lenguaje de reglas de negocio) en un solo archivo BRL antes de importar.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-355">You can merge two or more BRL (Business Rule Language XML file) files into a single BRL file before importing.</span></span> <span data-ttu-id="d6fbc-356">El código siguiente muestra tres archivos BRL.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-356">The following code shows three BRL files.</span></span> <span data-ttu-id="d6fbc-357">El primer archivo BRL contiene el **POVocabulary** vocabulario.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-357">The first BRL file contains the **POVocabulary** vocabulary.</span></span> <span data-ttu-id="d6fbc-358">El segundo archivo BRL contiene el **ProcessPurchaseOrder** directiva.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-358">The second BRL file contains the **ProcessPurchaseOrder** policy.</span></span> <span data-ttu-id="d6fbc-359">El tercer archivo BRL contiene tanto el **POVocabulary** vocabulario y el **ProcessPurchaseOrder** directiva.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-359">The third BRL file contains both the **POVocabulary** vocabulary and the **ProcessPurchaseOrder** policy.</span></span> <span data-ttu-id="d6fbc-360">Para realizar el tercer archivo BRL, realice estos pasos:</span><span class="sxs-lookup"><span data-stu-id="d6fbc-360">The third BRE file is created by performing the following steps:</span></span>  
  
    1.  <span data-ttu-id="d6fbc-361">Crear un nuevo archivo con cualquier archivo editor y guárdelo como un archivo XML (por ejemplo: POPolicyVocabulary.xml).</span><span class="sxs-lookup"><span data-stu-id="d6fbc-361">Create a new file using any file editor and save it as an XML file (for example: POPolicyVocabulary.xml).</span></span>  
  
    2.  <span data-ttu-id="d6fbc-362">Copie el contenido XML completo del primer archivo BRL que contiene el vocabulario.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-362">Copy the entire XML content from the first BRL file containing the vocabulary.</span></span>  
  
    3.  <span data-ttu-id="d6fbc-363">Copie el bloque del conjunto de reglas (comienza con la \<ruleset\> etiqueta y finaliza con la \</ruleset\> etiqueta) del segundo archivo BRL.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-363">Copy the ruleset block (starts with the \<ruleset\> tag and ends with the \</ruleset\> tag) from the second BRL file.</span></span>  
  
    4.  <span data-ttu-id="d6fbc-364">Guarde el archivo nuevo.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-364">Save the new file.</span></span> <span data-ttu-id="d6fbc-365">Puede importar este archivo XML único para crear el **POVocabulary** vocabulario y el **ProcessPurchaseOrder** directiva.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-365">You can import this single XML file to create the **POVocabulary** vocabulary and the **ProcessPurchaseOrder** policy.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d6fbc-366">El orden en que se enumeran los nodos vocabulary y ruleset en el archivo BRL combinado no es relevante.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-366">It does not matter in which order the vocabulary and ruleset nodes are listed in the merged BRL file.</span></span> <span data-ttu-id="d6fbc-367">Puede colocar el nodo ruleset antes que el nodo vocabulary.</span><span class="sxs-lookup"><span data-stu-id="d6fbc-367">You can have the ruleset node ahead of the vocabulary node.</span></span>  
  
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