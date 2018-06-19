---
title: Generar WSDL con el SDK del adaptador LOB de WCF | Documentos de Microsoft
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
ms.openlocfilehash: f1075bbe59e15e3eeabde6c1d5c954460d1cb570
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224612"
---
# <a name="generate-wsdl-with-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="3bf66-102">Generar WSDL con el SDK del adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="3bf66-102">Generate WSDL with the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="3bf66-103">Durante el desarrollo de un adaptador, o cuando los metadatos que se devuelven de los cambios del sistema LOB, a menudo resulta útil ver el lenguaje de descripción de servicios Web (WSDL) que se devuelve desde el adaptador para comprobar que se generan los metadatos para las operaciones correctamente.</span><span class="sxs-lookup"><span data-stu-id="3bf66-103">During development of an adapter, or when the metadata that is returned from the LOB system changes, it is often useful to view the Web Services Description Language (WSDL) that is returned from the adapter to verify that the metadata for your operations is generated correctly.</span></span> <span data-ttu-id="3bf66-104">Existen varios métodos para generar el WSDL.</span><span class="sxs-lookup"><span data-stu-id="3bf66-104">There are several methods to generate the WSDL.</span></span> <span data-ttu-id="3bf66-105">Este tema proporciona información acerca del uso de svcutil.exe y el control Buscar de búsqueda de metadatos.</span><span class="sxs-lookup"><span data-stu-id="3bf66-105">This topic provides information about using svcutil.exe and the Metadata Search Browse control.</span></span>  

  
## <a name="use-svcutilexe"></a><span data-ttu-id="3bf66-106">Utilizar svcutil.exe</span><span class="sxs-lookup"><span data-stu-id="3bf66-106">Use svcutil.exe</span></span>  
 <span data-ttu-id="3bf66-107">Svcutil.exe es una utilidad de línea de comandos incluida con el SDK de Windows que acepta una dirección URL y los modificadores opcionales y devuelve el WSDL.</span><span class="sxs-lookup"><span data-stu-id="3bf66-107">Svcutil.exe is a command-line utility shipped with the Windows SDK that accepts a URL and optional switches, and returns WSDL.</span></span> <span data-ttu-id="3bf66-108">El siguiente es un ejemplo del uso de svcutil.exe para devolver el WSDL del adaptador de eco:</span><span class="sxs-lookup"><span data-stu-id="3bf66-108">The following is an example of using svcutil.exe to return the WSDL of the Echo Adapter:</span></span>  
  
 ```
 Svcutil.exe “echov2://lobhostname/lobapplication?enableAuthentication=False” /target:metadata
 ```
  
 <span data-ttu-id="3bf66-109">Esto guarda los metadatos como Microsoft.Adapters.Samples.Echov2.wsdl.</span><span class="sxs-lookup"><span data-stu-id="3bf66-109">This saves the metadata as Microsoft.Adapters.Samples.Echov2.wsdl.</span></span> <span data-ttu-id="3bf66-110">Si el adaptador tiene muchas operaciones, puede hacer que devuelva solo las operaciones deseadas mediante ' op = OperationName' como parte del URI.</span><span class="sxs-lookup"><span data-stu-id="3bf66-110">If your adapter has many operations, you can choose to return only the desired operations by using ‘op=OperationName’ as part of the URI.</span></span> <span data-ttu-id="3bf66-111">El siguiente es un ejemplo de usar esto para devolver únicamente la información de EchoStrings:</span><span class="sxs-lookup"><span data-stu-id="3bf66-111">The following is an example of using this to return only the EchoStrings information:</span></span>  
  
```  
SvcUtil.exe “echov2://lobhostname/lobapplication?enableAuthentication=False&op=Echo/EchoStrings” /target:metadata  
```  
  
## <a name="use-the-metadata-search-browse-control"></a><span data-ttu-id="3bf66-112">Usar el Control de exploración de búsqueda de metadatos</span><span class="sxs-lookup"><span data-stu-id="3bf66-112">Use the Metadata Search Browse Control</span></span>  
 <span data-ttu-id="3bf66-113">El control examinar de búsqueda de metadatos es un control de Windows que se utiliza en los asistentes incluidos en [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3bf66-113">The Metadata Search Browse control is a Windows control that is used in the wizards included in [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="3bf66-114">Puede agregar este control a cualquier proyecto de formularios Windows Forms en Visual Studio y utilizarla para seleccionar el adaptador, las operaciones deseadas y, a continuación, genere el WSDL.</span><span class="sxs-lookup"><span data-stu-id="3bf66-114">You can add this control to any Windows Forms project in Visual Studio, and use it to select your adapter, the desired operations, and then generate the WSDL.</span></span>  
  
1.  <span data-ttu-id="3bf66-115">Abra un [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="3bf66-115">Open a [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] command prompt.</span></span>  
  
2.  <span data-ttu-id="3bf66-116">En el **archivo** menú, seleccione **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="3bf66-116">On the **File** menu, select **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="3bf66-117">En el **nuevo proyecto** cuadro de diálogo, seleccione **aplicación de Windows** de **plantillas**.</span><span class="sxs-lookup"><span data-stu-id="3bf66-117">In the **New Project** dialog box, select **Windows Application** from **Templates**.</span></span> <span data-ttu-id="3bf66-118">Escriba un nombre de proyecto y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3bf66-118">Enter a project name, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="3bf66-119">Abra la **cuadro de herramientas**, expanda **controles comunes**, haga clic en el **cuadro de herramientas**y, a continuación, haga clic en **elegir elementos**.</span><span class="sxs-lookup"><span data-stu-id="3bf66-119">Open the **Toolbox**, expand **Common Controls**, right-click the **Toolbox**, and then click **Choose Items**.</span></span>  
  
5.  <span data-ttu-id="3bf66-120">En el **elegir elementos del cuadro de herramientas** cuadro de diálogo Buscar **MetadataUserControl** en el **componentes de .NET Framework** ficha, active la casilla situada junto a este elemento y, a continuación, haga clic en  **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3bf66-120">In the **Choose Toolbox Items** dialog box, find **MetadataUserControl** on the **.NET Framework Components** tab, select the check box beside this item, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="3bf66-121">En el cuadro de herramientas, arrastre el MetadataUserControl hasta Form1.</span><span class="sxs-lookup"><span data-stu-id="3bf66-121">From the Toolbox, drag the MetadataUserControl to Form1.</span></span> <span data-ttu-id="3bf66-122">Debe cambiar el tamaño del formulario para ver todo el control.</span><span class="sxs-lookup"><span data-stu-id="3bf66-122">You may need to resize the form to see the entire control.</span></span> <span data-ttu-id="3bf66-123">Debe ser capaz de ejecutar el proyecto ahora y compruebe que el control está operativo, lo que le permite seleccionar un adaptador y operaciones.</span><span class="sxs-lookup"><span data-stu-id="3bf66-123">You should be able to run the project now and verify that the control is functional, allowing you to select an adapter and operations.</span></span>  
  
7.  <span data-ttu-id="3bf66-124">Para generar WSDL mediante el uso de este control, debe agregar código al formulario para llamar a la **GetWsdl** método de este control.</span><span class="sxs-lookup"><span data-stu-id="3bf66-124">To generate WSDL by using this control, you must add code to your form to call the **GetWsdl** method of this control.</span></span> <span data-ttu-id="3bf66-125">En el ejemplo siguiente se muestra cómo llamar a **GetWsdl** y guardar los datos en el archivo:</span><span class="sxs-lookup"><span data-stu-id="3bf66-125">The following example demonstrates how to call **GetWsdl** and save the data to file:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3bf66-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="3bf66-126">See Also</span></span>  
 [<span data-ttu-id="3bf66-127">Solucionar problemas del adaptador creado mediante el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="3bf66-127">Troubleshoot adapter created using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/troubleshoot-adapter-created-using-the-wcf-lob-adapter-sdk.md)