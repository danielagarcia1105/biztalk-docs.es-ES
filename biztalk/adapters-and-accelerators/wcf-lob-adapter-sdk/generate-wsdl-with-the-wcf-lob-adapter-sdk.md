---
title: Generar WSDL con el SDK del adaptador LOB de WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f701d78d-b3ad-4f75-b814-e5b1f1319fb9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eaf5ed992864c11d360baa30f35983f0082213b3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971077"
---
# <a name="generate-wsdl-with-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="645ee-102">Generar WSDL con el SDK del adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="645ee-102">Generate WSDL with the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="645ee-103">Durante el desarrollo de un adaptador, o cuando los metadatos que se devuelven de los cambios del sistema LOB, a menudo es útil ver el lenguaje de descripción de servicios Web (WSDL) que se devuelve desde el adaptador para comprobar que se generan los metadatos para las operaciones correctamente.</span><span class="sxs-lookup"><span data-stu-id="645ee-103">During development of an adapter, or when the metadata that is returned from the LOB system changes, it is often useful to view the Web Services Description Language (WSDL) that is returned from the adapter to verify that the metadata for your operations is generated correctly.</span></span> <span data-ttu-id="645ee-104">Existen varios métodos para generar el WSDL.</span><span class="sxs-lookup"><span data-stu-id="645ee-104">There are several methods to generate the WSDL.</span></span> <span data-ttu-id="645ee-105">En este tema se proporciona información sobre el uso de svcutil.exe y el control de búsqueda de metadatos Examinar.</span><span class="sxs-lookup"><span data-stu-id="645ee-105">This topic provides information about using svcutil.exe and the Metadata Search Browse control.</span></span>  

  
## <a name="use-svcutilexe"></a><span data-ttu-id="645ee-106">Utilice svcutil.exe</span><span class="sxs-lookup"><span data-stu-id="645ee-106">Use svcutil.exe</span></span>  
 <span data-ttu-id="645ee-107">Svcutil.exe es una utilidad de línea de comandos se incluye con el SDK de Windows que acepta una dirección URL y modificadores opcionales y devuelve el WSDL.</span><span class="sxs-lookup"><span data-stu-id="645ee-107">Svcutil.exe is a command-line utility shipped with the Windows SDK that accepts a URL and optional switches, and returns WSDL.</span></span> <span data-ttu-id="645ee-108">El siguiente es un ejemplo del uso de svcutil.exe para devolver el WSDL del adaptador de Echo:</span><span class="sxs-lookup"><span data-stu-id="645ee-108">The following is an example of using svcutil.exe to return the WSDL of the Echo Adapter:</span></span>  
  
 ```
 Svcutil.exe “echov2://lobhostname/lobapplication?enableAuthentication=False” /target:metadata
 ```
  
 <span data-ttu-id="645ee-109">Esto guarda los metadatos como Microsoft.Adapters.Samples.Echov2.wsdl.</span><span class="sxs-lookup"><span data-stu-id="645ee-109">This saves the metadata as Microsoft.Adapters.Samples.Echov2.wsdl.</span></span> <span data-ttu-id="645ee-110">Si el adaptador tiene muchas operaciones, puede elegir devolver sólo las operaciones deseadas mediante el uso de ' op = OperationName' como parte del URI.</span><span class="sxs-lookup"><span data-stu-id="645ee-110">If your adapter has many operations, you can choose to return only the desired operations by using ‘op=OperationName’ as part of the URI.</span></span> <span data-ttu-id="645ee-111">Este es un ejemplo del uso esto para devolver únicamente la información de EchoStrings:</span><span class="sxs-lookup"><span data-stu-id="645ee-111">The following is an example of using this to return only the EchoStrings information:</span></span>  
  
```  
SvcUtil.exe “echov2://lobhostname/lobapplication?enableAuthentication=False&op=Echo/EchoStrings” /target:metadata  
```  
  
## <a name="use-the-metadata-search-browse-control"></a><span data-ttu-id="645ee-112">Utilice el Control de exploración de la búsqueda de metadatos</span><span class="sxs-lookup"><span data-stu-id="645ee-112">Use the Metadata Search Browse Control</span></span>  
 <span data-ttu-id="645ee-113">El control de búsqueda de metadatos examinar es un control de Windows que se usa en los asistentes incluidos en [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="645ee-113">The Metadata Search Browse control is a Windows control that is used in the wizards included in [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="645ee-114">Puede agregar este control a cualquier proyecto de Windows Forms en Visual Studio y usarla para seleccionar el adaptador, las operaciones deseadas y, a continuación, generar el WSDL.</span><span class="sxs-lookup"><span data-stu-id="645ee-114">You can add this control to any Windows Forms project in Visual Studio, and use it to select your adapter, the desired operations, and then generate the WSDL.</span></span>  
  
1. <span data-ttu-id="645ee-115">Abra un [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="645ee-115">Open a [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] command prompt.</span></span>  
  
2. <span data-ttu-id="645ee-116">En el **archivo** menú, seleccione **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="645ee-116">On the **File** menu, select **New**, and then click **Project**.</span></span>  
  
3. <span data-ttu-id="645ee-117">En el **nuevo proyecto** cuadro de diálogo, seleccione **aplicación Windows** desde **plantillas**.</span><span class="sxs-lookup"><span data-stu-id="645ee-117">In the **New Project** dialog box, select **Windows Application** from **Templates**.</span></span> <span data-ttu-id="645ee-118">Escriba un nombre de proyecto y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="645ee-118">Enter a project name, and then click **OK**.</span></span>  
  
4. <span data-ttu-id="645ee-119">Abra el **cuadro de herramientas**, expanda **controles comunes**, haga clic en el **cuadro de herramientas**y, a continuación, haga clic en **elegir elementos**.</span><span class="sxs-lookup"><span data-stu-id="645ee-119">Open the **Toolbox**, expand **Common Controls**, right-click the **Toolbox**, and then click **Choose Items**.</span></span>  
  
5. <span data-ttu-id="645ee-120">En el **elegir elementos del cuadro de herramientas** cuadro de diálogo, busque **MetadataUserControl** en el **componentes de .NET Framework** , seleccione la casilla de verificación situada junto a este elemento y, a continuación, haga clic en  **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="645ee-120">In the **Choose Toolbox Items** dialog box, find **MetadataUserControl** on the **.NET Framework Components** tab, select the check box beside this item, and then click **OK**.</span></span>  
  
6. <span data-ttu-id="645ee-121">En el cuadro de herramientas, arrastre el MetadataUserControl a Form1.</span><span class="sxs-lookup"><span data-stu-id="645ee-121">From the Toolbox, drag the MetadataUserControl to Form1.</span></span> <span data-ttu-id="645ee-122">Deberá cambiar el tamaño del formulario para ver todo el control.</span><span class="sxs-lookup"><span data-stu-id="645ee-122">You may need to resize the form to see the entire control.</span></span> <span data-ttu-id="645ee-123">Debe ser capaz de ejecutar el proyecto ahora y compruebe que el control es funcional, que le permite seleccionar un adaptador y las operaciones.</span><span class="sxs-lookup"><span data-stu-id="645ee-123">You should be able to run the project now and verify that the control is functional, allowing you to select an adapter and operations.</span></span>  
  
7. <span data-ttu-id="645ee-124">Para generar WSDL mediante el uso de este control, debe agregar código al formulario para llamar a la **GetWsdl** método de este control.</span><span class="sxs-lookup"><span data-stu-id="645ee-124">To generate WSDL by using this control, you must add code to your form to call the **GetWsdl** method of this control.</span></span> <span data-ttu-id="645ee-125">En el ejemplo siguiente se muestra cómo llamar a **GetWsdl** y guardar los datos en el archivo:</span><span class="sxs-lookup"><span data-stu-id="645ee-125">The following example demonstrates how to call **GetWsdl** and save the data to file:</span></span>  
  
   ```csharp  
   private void button1_Click(object sender, EventArgs e)  
   {  
      ServiceDescription sd = mdUserControl.GetWsdl();  
      FileStream myFileStream = new FileStream(tbWsdlFileName.Text, FileMode.OpenOrCreate, FileAccess.Write);  
      StreamWriter myStreamWriter = new StreamWriter(myFileStream);  
      sd.Write(myStreamWriter);  
      myStreamWriter.Flush();  
      myStreamWriter.Close();  
      MessageBox.Show("WSDL file " + tbWsdlFileName.Text + " is created.");  
   }  
  
   ```  
  
## <a name="see-also"></a><span data-ttu-id="645ee-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="645ee-126">See Also</span></span>  
 [<span data-ttu-id="645ee-127">Solución de problemas de adaptador creado mediante el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="645ee-127">Troubleshoot adapter created using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/troubleshoot-adapter-created-using-the-wcf-lob-adapter-sdk.md)