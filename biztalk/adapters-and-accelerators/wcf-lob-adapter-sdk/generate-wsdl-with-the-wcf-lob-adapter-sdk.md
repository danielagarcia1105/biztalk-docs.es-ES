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
# <a name="generate-wsdl-with-the-wcf-lob-adapter-sdk"></a>Generar WSDL con el SDK del adaptador LOB de WCF
Durante el desarrollo de un adaptador, o cuando los metadatos que se devuelven de los cambios del sistema LOB, a menudo resulta útil ver el lenguaje de descripción de servicios Web (WSDL) que se devuelve desde el adaptador para comprobar que se generan los metadatos para las operaciones correctamente. Existen varios métodos para generar el WSDL. Este tema proporciona información acerca del uso de svcutil.exe y el control Buscar de búsqueda de metadatos.  

  
## <a name="use-svcutilexe"></a>Utilizar svcutil.exe  
 Svcutil.exe es una utilidad de línea de comandos incluida con el SDK de Windows que acepta una dirección URL y los modificadores opcionales y devuelve el WSDL. El siguiente es un ejemplo del uso de svcutil.exe para devolver el WSDL del adaptador de eco:  
  
 ```
 Svcutil.exe “echov2://lobhostname/lobapplication?enableAuthentication=False” /target:metadata
 ```
  
 Esto guarda los metadatos como Microsoft.Adapters.Samples.Echov2.wsdl. Si el adaptador tiene muchas operaciones, puede hacer que devuelva solo las operaciones deseadas mediante ' op = OperationName' como parte del URI. El siguiente es un ejemplo de usar esto para devolver únicamente la información de EchoStrings:  
  
```  
SvcUtil.exe “echov2://lobhostname/lobapplication?enableAuthentication=False&op=Echo/EchoStrings” /target:metadata  
```  
  
## <a name="use-the-metadata-search-browse-control"></a>Usar el Control de exploración de búsqueda de metadatos  
 El control examinar de búsqueda de metadatos es un control de Windows que se utiliza en los asistentes incluidos en [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. Puede agregar este control a cualquier proyecto de formularios Windows Forms en Visual Studio y utilizarla para seleccionar el adaptador, las operaciones deseadas y, a continuación, genere el WSDL.  
  
1.  Abra un [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] símbolo del sistema.  
  
2.  En el **archivo** menú, seleccione **New**y, a continuación, haga clic en **proyecto**.  
  
3.  En el **nuevo proyecto** cuadro de diálogo, seleccione **aplicación de Windows** de **plantillas**. Escriba un nombre de proyecto y, a continuación, haga clic en **Aceptar**.  
  
4.  Abra la **cuadro de herramientas**, expanda **controles comunes**, haga clic en el **cuadro de herramientas**y, a continuación, haga clic en **elegir elementos**.  
  
5.  En el **elegir elementos del cuadro de herramientas** cuadro de diálogo Buscar **MetadataUserControl** en el **componentes de .NET Framework** ficha, active la casilla situada junto a este elemento y, a continuación, haga clic en  **Aceptar**.  
  
6.  En el cuadro de herramientas, arrastre el MetadataUserControl hasta Form1. Debe cambiar el tamaño del formulario para ver todo el control. Debe ser capaz de ejecutar el proyecto ahora y compruebe que el control está operativo, lo que le permite seleccionar un adaptador y operaciones.  
  
7.  Para generar WSDL mediante el uso de este control, debe agregar código al formulario para llamar a la **GetWsdl** método de este control. En el ejemplo siguiente se muestra cómo llamar a **GetWsdl** y guardar los datos en el archivo:  
  
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
  
## <a name="see-also"></a>Vea también  
 [Solucionar problemas del adaptador creado mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/troubleshoot-adapter-created-using-the-wcf-lob-adapter-sdk.md)