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
# <a name="generate-wsdl-with-the-wcf-lob-adapter-sdk"></a>Generar WSDL con el SDK del adaptador LOB de WCF
Durante el desarrollo de un adaptador, o cuando los metadatos que se devuelven de los cambios del sistema LOB, a menudo es útil ver el lenguaje de descripción de servicios Web (WSDL) que se devuelve desde el adaptador para comprobar que se generan los metadatos para las operaciones correctamente. Existen varios métodos para generar el WSDL. En este tema se proporciona información sobre el uso de svcutil.exe y el control de búsqueda de metadatos Examinar.  

  
## <a name="use-svcutilexe"></a>Utilice svcutil.exe  
 Svcutil.exe es una utilidad de línea de comandos se incluye con el SDK de Windows que acepta una dirección URL y modificadores opcionales y devuelve el WSDL. El siguiente es un ejemplo del uso de svcutil.exe para devolver el WSDL del adaptador de Echo:  
  
 ```
 Svcutil.exe “echov2://lobhostname/lobapplication?enableAuthentication=False” /target:metadata
 ```
  
 Esto guarda los metadatos como Microsoft.Adapters.Samples.Echov2.wsdl. Si el adaptador tiene muchas operaciones, puede elegir devolver sólo las operaciones deseadas mediante el uso de ' op = OperationName' como parte del URI. Este es un ejemplo del uso esto para devolver únicamente la información de EchoStrings:  
  
```  
SvcUtil.exe “echov2://lobhostname/lobapplication?enableAuthentication=False&op=Echo/EchoStrings” /target:metadata  
```  
  
## <a name="use-the-metadata-search-browse-control"></a>Utilice el Control de exploración de la búsqueda de metadatos  
 El control de búsqueda de metadatos examinar es un control de Windows que se usa en los asistentes incluidos en [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. Puede agregar este control a cualquier proyecto de Windows Forms en Visual Studio y usarla para seleccionar el adaptador, las operaciones deseadas y, a continuación, generar el WSDL.  
  
1. Abra un [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] símbolo del sistema.  
  
2. En el **archivo** menú, seleccione **New**y, a continuación, haga clic en **proyecto**.  
  
3. En el **nuevo proyecto** cuadro de diálogo, seleccione **aplicación Windows** desde **plantillas**. Escriba un nombre de proyecto y, a continuación, haga clic en **Aceptar**.  
  
4. Abra el **cuadro de herramientas**, expanda **controles comunes**, haga clic en el **cuadro de herramientas**y, a continuación, haga clic en **elegir elementos**.  
  
5. En el **elegir elementos del cuadro de herramientas** cuadro de diálogo, busque **MetadataUserControl** en el **componentes de .NET Framework** , seleccione la casilla de verificación situada junto a este elemento y, a continuación, haga clic en  **Aceptar**.  
  
6. En el cuadro de herramientas, arrastre el MetadataUserControl a Form1. Deberá cambiar el tamaño del formulario para ver todo el control. Debe ser capaz de ejecutar el proyecto ahora y compruebe que el control es funcional, que le permite seleccionar un adaptador y las operaciones.  
  
7. Para generar WSDL mediante el uso de este control, debe agregar código al formulario para llamar a la **GetWsdl** método de este control. En el ejemplo siguiente se muestra cómo llamar a **GetWsdl** y guardar los datos en el archivo:  
  
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
 [Solución de problemas de adaptador creado mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/troubleshoot-adapter-created-using-the-wcf-lob-adapter-sdk.md)