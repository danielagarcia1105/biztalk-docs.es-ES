---
title: 'Paso 4: Crear el proyecto HeaderHelper | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects, helper projects
- private process tutorial, creating helper projects
ms.assetid: 82413537-032a-4368-8d77-d024a7c83b0b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2525e0e87106e2eeb82fb05b52b3ec69d4be876d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-4-creating-the-headerhelper-project"></a><span data-ttu-id="c7608-102">Paso 4: Crear el proyecto HeaderHelper</span><span class="sxs-lookup"><span data-stu-id="c7608-102">Step 4: Creating the HeaderHelper Project</span></span>
<span data-ttu-id="c7608-103">En este paso, creará un [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="c7608-103">In this step, you create a [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] class library.</span></span> <span data-ttu-id="c7608-104">Cuando una orquestación de procesos privados recibe un mensaje entrante, la biblioteca de HeaderHelper determina si una conversión de documento es necesaria y si es necesario, realiza esa conversión.</span><span class="sxs-lookup"><span data-stu-id="c7608-104">When a private process orchestration receives an incoming message, the HeaderHelper library determines whether a document conversion is required and if it is required, performs that conversion.</span></span> <span data-ttu-id="c7608-105">Esto permite que la orquestación trabajar con distintas versiones de documentos de RosettaNet Implementation Framework (RNIF).</span><span class="sxs-lookup"><span data-stu-id="c7608-105">This lets your orchestration work with different versions of RosettaNet Implementation Framework (RNIF) documents.</span></span> <span data-ttu-id="c7608-106">Además, cuando se envía un mensaje de respuesta de 3A2, la biblioteca HeaderHelper realiza una conversión de documento adicionales antes de transmitir el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c7608-106">Additionally, when a 3A2 response message is sent, the HeaderHelper library performs an additional document conversion before transmitting the message.</span></span>  
  
### <a name="to-create-the-headerhelper-project"></a><span data-ttu-id="c7608-107">Para crear el proyecto HeaderHelper</span><span class="sxs-lookup"><span data-stu-id="c7608-107">To create the HeaderHelper project</span></span>  
  
1.  <span data-ttu-id="c7608-108">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en el Explorador de soluciones, haga clic en la solución de Contoso, seleccione **agregar**y, a continuación, haga clic en **nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="c7608-108">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], in Solution Explorer, right-click the Contoso solution, point to **Add**, and then click **New Project**.</span></span>  
  
2.  <span data-ttu-id="c7608-109">En el cuadro de diálogo Agregar nuevo proyecto, en el panel tipos de proyecto, seleccione **Visual C#**.</span><span class="sxs-lookup"><span data-stu-id="c7608-109">In the Add New Project dialog box, in the Project Types pane, select **Visual C#**.</span></span>  
  
3.  <span data-ttu-id="c7608-110">En el panel Plantillas, seleccione la **biblioteca de clases** plantilla.</span><span class="sxs-lookup"><span data-stu-id="c7608-110">In the Templates pane, select the **Class Library** template.</span></span>  
  
4.  <span data-ttu-id="c7608-111">En el **nombre** , escriba **HeaderHelper**y, a continuación, haga clic en **Aceptar** para crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c7608-111">In the **Name** box, type **HeaderHelper**, and then click **OK** to create the project.</span></span>  
  
5.  <span data-ttu-id="c7608-112">En el Explorador de soluciones, haga clic con el **Class1.cs** un archivo en el **HeaderHelper** proyecto de equipo y haga clic en **cambiar el nombre de**, tipo **HeaderHelper.cs**, y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="c7608-112">In Solution Explorer, right click the **Class1.cs** file in the **HeaderHelper** project, click **Rename**, type **HeaderHelper.cs**, and then press **Enter**.</span></span>  
  
### <a name="to-create-the-helper-class"></a><span data-ttu-id="c7608-113">Para crear la clase auxiliar</span><span class="sxs-lookup"><span data-stu-id="c7608-113">To create the Helper class</span></span>  
  
1.  <span data-ttu-id="c7608-114">En el Explorador de soluciones, expanda la **HeaderHelper** del proyecto y, a continuación, haga doble clic en el **HeaderHelper.cs** nodo para abrir el archivo de origen HeaderHelper.</span><span class="sxs-lookup"><span data-stu-id="c7608-114">In Solution Explorer, expand the **HeaderHelper** project, and then double-click the **HeaderHelper.cs** node to open the HeaderHelper source file.</span></span>  
  
2.  <span data-ttu-id="c7608-115">Escriba el código siguiente en el archivo de código fuente, sobrescribir todo el código existente:</span><span class="sxs-lookup"><span data-stu-id="c7608-115">Type the following code into the source file, overwriting all the existing code:</span></span>  
  
    ```  
    using System;  
    using System.Xml;  
  
    namespace ContosoPriceAndAvailability  
    {  
        public class Helper  
        {  
            static public XmlDocument NormalizeHeader( XmlDocument curPip )  
            {  
                string strInput = curPip.OuterXml;  
                try  
                {  
                    XmlDocument xDoc = new XmlDocument();  
  
                    strInput = strInput.Replace("<!DOCTYPE Pip3A2PriceAndAvailabilityQuery SYSTEM \"3A2PriceAndAvailabilityQueryMessageGuideline_v1_3.dtd\"[]>",String.Empty);  
                    strInput = strInput.Replace("<Pip3A2PriceAndAvailabilityQuery>","<Pip3A2PriceAndAvailabilityQuery xmlns=\"http://schemas.microsoft.com/biztalk/btarn/2004/3A2PriceAndAvailabilityQueryMessageGuideline_v1_3.dtd\">");  
                    strInput = strInput.Replace("xml:",String.Empty);  
                    strInput = strInput.Replace("b:",String.Empty);  
                    strInput = strInput.Replace("lang:",String.Empty);  
                    strInput = strInput.Replace("ns1:",String.Empty);  
  
                    xDoc.LoadXml(strInput);  
  
                    return xDoc;  
                }  
                catch(Exception ex)  
                {  
                    System.Diagnostics.Debug.Write( ex.Message );  
                    throw ex;  
                }  
            }  
  
            static public string ReturnSCWithDocType( XmlDocument xmlDoc )  
            {  
                try  
                {  
                    string sResponse = xmlDoc.InnerXml;  
                    sResponse=sResponse.Replace("ns0:",String.Empty);  
                    xmlDoc.LoadXml(sResponse);  
                    xmlDoc.DocumentElement.RemoveAllAttributes();  
                    sResponse = xmlDoc.InnerXml;  
  
                    sResponse = sResponse.Insert(0,"<!DOCTYPE Pip3A2PriceAndAvailabilityResponse SYSTEM \"3A2PriceAndAvailabilityResponseMessageGuideline_v1_3.dtd\">");  
                    sResponse = sResponse.Replace("ns0:",String.Empty);  
                    sResponse = sResponse.Replace("b:",String.Empty);  
                    sResponse = sResponse.Replace("lang:",String.Empty);  
                    sResponse = sResponse.Replace("ns1:",String.Empty);  
  
                    return sResponse;  
                }  
                catch(Exception ex)  
                {  
                    throw ex;  
                }  
            }  
        }  
    }  
    ```  
  
3.  <span data-ttu-id="c7608-116">En el menú **Archivo** , haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="c7608-116">On the **File** menu, click **Save All**.</span></span>  
  
### <a name="to-create-a-strong-named-assembly-for-the-headerhelper-project"></a><span data-ttu-id="c7608-117">Para crear un ensamblado con nombre seguro para el proyecto HeaderHelper</span><span class="sxs-lookup"><span data-stu-id="c7608-117">To create a strong named assembly for the HeaderHelper project</span></span>  
  
1.  <span data-ttu-id="c7608-118">En el Explorador de soluciones, haga clic en el **HeaderHelper** del proyecto y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c7608-118">In Solution Explorer, right-click the **HeaderHelper** project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="c7608-119">En el cuadro de diálogo páginas de propiedades de HeaderHelper, seleccione **firma** en el panel izquierdo del panel de propiedades HeaderHelp.</span><span class="sxs-lookup"><span data-stu-id="c7608-119">In the HeaderHelper Property Pages dialog box, select **Signing** in the left pane of the HeaderHelp properties pane.</span></span>  
  
3.  <span data-ttu-id="c7608-120">En el panel derecho, haga clic en **firmar el ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="c7608-120">In the right pane, click **Sign the Assembly**.</span></span>  
  
4.  <span data-ttu-id="c7608-121">Haga clic en el **elegir un archivo de clave de nombre seguro** cuadro de texto y, a continuación, seleccione  **\<examinar\>**  en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="c7608-121">Click the **Choose a strong name key file** text box, and then select **\<Browse\>** from the drop-down list.</span></span>  
  
5.  <span data-ttu-id="c7608-122">En el cuadro de diálogo Seleccionar archivo, desplácese a la ubicación del ensamblado de Contoso y haga doble clic en **FabConPriceAvail.snk**.</span><span class="sxs-lookup"><span data-stu-id="c7608-122">In the Select File dialog box, move to the location of your Contoso assembly, and double-click **FabConPriceAvail.snk**.</span></span>  
  
6.  <span data-ttu-id="c7608-123">En el menú **Archivo** , haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="c7608-123">On the **File** menu, click **Save All**.</span></span>  
  
7.  <span data-ttu-id="c7608-124">En el Explorador de soluciones, expanda la **HeaderHelper** proyecto de equipo y expanda el **propiedades** nodo y, a continuación, haga doble clic en el **AssemblyInfo.cs** nodo para abrir el archivo AssemblyInfo.cs archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="c7608-124">In Solution Explorer, expand the **HeaderHelper** project, expand the **Properties** node, and then double-click the **AssemblyInfo.cs** node to open the AssemblyInfo.cs source file.</span></span>  
  
8.  <span data-ttu-id="c7608-125">En el archivo de origen AssemblyInfo.cs, escriba el código siguiente en la línea después del atributo AssemblyCulture:</span><span class="sxs-lookup"><span data-stu-id="c7608-125">In the AssemblyInfo.cs source file, type the following code on the line after the AssemblyCulture attribute:</span></span>  
  
    ```  
    [assembly: AssemblyKeyFile("../../../FabConPriceAvail.snk")]  
    ```  
  
9. <span data-ttu-id="c7608-126">En el menú **Archivo** , haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="c7608-126">On the **File** menu, click **Save All**.</span></span>  
  
### <a name="to-build-and-deploy-the-headerhelper-project"></a><span data-ttu-id="c7608-127">Para compilar e implementar el proyecto HeaderHelper</span><span class="sxs-lookup"><span data-stu-id="c7608-127">To build and deploy the HeaderHelper project</span></span>  
  
1.  <span data-ttu-id="c7608-128">En el Explorador de soluciones, haga clic en el **HeaderHelper** del proyecto y, a continuación, haga clic en **generar**.</span><span class="sxs-lookup"><span data-stu-id="c7608-128">In Solution Explorer, right-click the **HeaderHelper** project, and then click **Build**.</span></span>  
  
2.  <span data-ttu-id="c7608-129">Inicie un **símbolo del sistema de Visual Studio 2012**.</span><span class="sxs-lookup"><span data-stu-id="c7608-129">Start **Visual Studio 2012 Command Prompt**.</span></span>  
  
3.  <span data-ttu-id="c7608-130">En el símbolo del sistema, desplácese a la ubicación de la **HeaderHelper** el directorio de salida del proyecto (la carpeta \Bin\Debug).</span><span class="sxs-lookup"><span data-stu-id="c7608-130">At the command prompt, move to the location of the **HeaderHelper** project output directory (the \Bin\Debug folder).</span></span>  
  
4.  <span data-ttu-id="c7608-131">En el símbolo del sistema, escriba **gacutil /if HeaderHelper.dll** y presione **ENTRAR** para instalar el **HeaderHelper** ensamblado en el **caché Global de ensamblados** .</span><span class="sxs-lookup"><span data-stu-id="c7608-131">At the command prompt, type **gacutil /if HeaderHelper.dll** and press **Enter** to install the **HeaderHelper** assembly into the **Global Assembly Cache**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7608-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7608-132">See Also</span></span>  
 [<span data-ttu-id="c7608-133">Paso 5: Modificación de la orquestación de procesos privados de Contoso</span><span class="sxs-lookup"><span data-stu-id="c7608-133">Step 5: Modifying the Contoso Private Process Orchestration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-5-modifying-the-contoso-private-process-orchestration.md)