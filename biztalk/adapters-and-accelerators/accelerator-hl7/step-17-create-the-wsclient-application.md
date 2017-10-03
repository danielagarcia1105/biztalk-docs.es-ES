---
title: "Paso 17: Crear la aplicación WSClient | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WSClient application
- message enrichment tutorial, WSClient application
- creating, WSClient application
ms.assetid: 2849cd4c-30d0-47ab-8161-fab379d5a548
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8028688f918854d8251f7b059c76642800961088
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-17-create-the-wsclient-application"></a><span data-ttu-id="4ca81-102">Paso 17: Crear la aplicación WSClient</span><span class="sxs-lookup"><span data-stu-id="4ca81-102">Step 17: Create the WSClient Application</span></span>
<span data-ttu-id="4ca81-103">WSClient.exe (cliente de servicios Web) es una aplicación de consola escrita en [!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)] que muestra cómo enviar datos a la orquestación que se publicó como un servicio Web en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="4ca81-103">WSClient.exe (Web service client) is a console application written in [!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)] that illustrates how to send data to the orchestration that you published as a Web service in the previous steps.</span></span> <span data-ttu-id="4ca81-104">La aplicación WSClient acepta cuatro parámetros en orden de entrada: nombre del paciente primero, segundo nombre, apellido y número del seguro social, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="4ca81-104">The WSClient application accepts four input parameters in order: patient first name, middle name, last name, and social security number, respectively.</span></span> <span data-ttu-id="4ca81-105">Para enviar la información del paciente a su servicio Web, use la siguiente sintaxis de línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="4ca81-105">To send patient information to your Web service, use the following command line syntax:</span></span>  
  
```  
wsclient john henry smith 123456789  
```  
  
### <a name="to-create-the-wsclient-application"></a><span data-ttu-id="4ca81-106">Para crear la aplicación WSClient</span><span class="sxs-lookup"><span data-stu-id="4ca81-106">To create the WSClient application</span></span>  
  
1.  <span data-ttu-id="4ca81-107">En el Explorador de soluciones, haga clic en **solución 'BTAHL7V22Common'**, haga clic en **agregar**y, a continuación, haga clic en **nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="4ca81-107">In Solution Explorer, right-click **Solution 'BTAHL7V22Common'**, click **Add**, and then click **New Project**.</span></span>  
  
2.  <span data-ttu-id="4ca81-108">En el **Agregar nuevo proyecto** cuadro de diálogo, en la **tipos de proyecto** panel, haga clic en **Visual C#** y en el **plantillas** panel, haga clic en **Aplicación de consola**.</span><span class="sxs-lookup"><span data-stu-id="4ca81-108">In the **Add New Project** dialog box, in the **Project Types** pane, click **Visual C#** and in the **Templates** pane, click **Console Application**.</span></span>  
  
3.  <span data-ttu-id="4ca81-109">En el **nombre** , escriba **WSClient**.</span><span class="sxs-lookup"><span data-stu-id="4ca81-109">In the **Name** field, type **WSClient**.</span></span> <span data-ttu-id="4ca81-110">En el **ubicación** campo, vaya a  **\<* unidad*>: \Tutorial** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4ca81-110">In the **Location** field, browse to **\<*drive*>:\Tutorial**, and then click **OK**.</span></span> <span data-ttu-id="4ca81-111">El Explorador de soluciones agrega WSClient al árbol y aparece el archivo Program.cs.</span><span class="sxs-lookup"><span data-stu-id="4ca81-111">Solution Explorer adds WSClient to the tree, and the Program.cs file appears.</span></span>  
  
4.  <span data-ttu-id="4ca81-112">En el Explorador de soluciones, haga clic en **WSClient**y, a continuación, haga clic en **Agregar referencia Web**.</span><span class="sxs-lookup"><span data-stu-id="4ca81-112">In Solution Explorer, right-click **WSClient**, and then click **Add Web Reference**.</span></span>  
  
5.  <span data-ttu-id="4ca81-113">En el cuadro de diálogo Agregar referencia Web, haga clic en **Web services en el equipo local**.</span><span class="sxs-lookup"><span data-stu-id="4ca81-113">In the Add Web Reference dialog box, click **Web services on the local machine**.</span></span> <span data-ttu-id="4ca81-114">El equipo local busca servicios Web disponibles y, a continuación, muestra en una lista.</span><span class="sxs-lookup"><span data-stu-id="4ca81-114">The local computer searches for available Web services, and then displays them in a list.</span></span>  
  
6.  <span data-ttu-id="4ca81-115">En la lista de servicios Web en el equipo Local, haga clic en **BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**, haga clic en **Operation_1**y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="4ca81-115">In the list of Web Services on the Local Machine, click **BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**, click **Operation_1**, and then click **Add Reference**.</span></span>  
  
7.  <span data-ttu-id="4ca81-116">Haga doble clic en Program.cs.</span><span class="sxs-lookup"><span data-stu-id="4ca81-116">Double-click Program.cs.</span></span>  
  
8.  <span data-ttu-id="4ca81-117">Copie el código siguiente y, a continuación, péguelo en la ventana de Program.cs:</span><span class="sxs-lookup"><span data-stu-id="4ca81-117">Copy the following code and then paste it into the Program.cs window:</span></span>  
  
    ```  
    using System;  
  
    namespace WSClient  
    {  
       class Class1  
       {  
          [STAThread]  
          static void Main(string[] args)  
          {  
             try   
             {  
                localhost.DoorbellRoot req=new WSClient.localhost.DoorbellRoot();  
                req.FirstName=args[0];  
                req.MiddleName=args[1];  
                req.LastName=args[2];  
                req.SSN=args[3];  
                localhost.BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort sp=new WSClient.localhost.BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort();  
                sp.Operation_1(req);  
             }  
             catch (Exception ex)  
             {  
                Console.WriteLine(ex.Message);  
             }  
          }  
       }  
    }  
    ```  
  
9. <span data-ttu-id="4ca81-118">En el Explorador de soluciones, haga clic en **WSClient**y, a continuación, haga clic en **generar**.</span><span class="sxs-lookup"><span data-stu-id="4ca81-118">In Solution Explorer, right-click **WSClient**, and then click **Build**.</span></span> <span data-ttu-id="4ca81-119">Asegúrese de que aparece un mensaje de confirmación en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="4ca81-119">Ensure that a success message appears in the output window.</span></span> <span data-ttu-id="4ca81-120">Si no aparece ningún mensaje de correcto, solucione **WSClient**.</span><span class="sxs-lookup"><span data-stu-id="4ca81-120">If no success message appears, troubleshoot **WSClient**.</span></span> [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="4ca81-121">coloca una copia del archivo ejecutable, WSClient.exe, en la \< *unidad*>: \Tutorial\WSClient\bin\Debug carpeta.</span><span class="sxs-lookup"><span data-stu-id="4ca81-121"> places a copy of the executable, WSClient.exe, into the \<*drive*>:\Tutorial\WSClient\bin\Debug folder.</span></span>  
  
 <span data-ttu-id="4ca81-122">Continúe con [paso 18: probar la nueva solución de enriquecimiento de mensaje](../../adapters-and-accelerators/accelerator-hl7/step-18-test-your-new-message-enrichment-solution.md).</span><span class="sxs-lookup"><span data-stu-id="4ca81-122">Proceed to [Step 18: Test Your New Message Enrichment Solution](../../adapters-and-accelerators/accelerator-hl7/step-18-test-your-new-message-enrichment-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ca81-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ca81-123">See Also</span></span>  
 [<span data-ttu-id="4ca81-124">Tutorial de enriquecimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="4ca81-124">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)