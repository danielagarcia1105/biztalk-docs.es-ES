---
title: Generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución de Siebel | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, generate a client class by using svcutil.exe
- creating a proxy
- how to, create a proxy
- WCF service model, creating a proxy
- how to, generate a client class by using the Add Adapter Service Reference Plug-in
- how to, generate a client class
ms.assetid: 52c32c86-6403-4bb4-9d43-1319d19a6b49
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c75615f0e6a3f6e4c947a7c13888558b7a666e77
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222412"
---
# <a name="generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts"></a>Generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución de Siebel
Puede usar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] generar una clase de cliente WCF destinada a operaciones seleccionadas en artefactos de Siebel. También puede usar la herramienta de utilidad de metadatos de ServiceModel (svcutil.exe) para generar la clase de cliente WCF; Sin embargo, la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] expone la funcionalidad de la herramienta de utilidad de metadatos de ServiceModel mediante una interfaz estándar de Microsoft Windows. También proporciona capacidades de exploración y búsqueda que no están disponibles con la herramienta svcutil.exe y genera un archivo de configuración basado en las propiedades de enlace que seleccionó al conectarse al sistema Siebel.  
  
## <a name="generating-a-wcf-client-class-by-using-the-add-adapter-service-reference-plug-in"></a>Generar una clase de cliente WCF mediante el Agregar referencia de servicio de adaptador complemento  
 Realice los pasos siguientes para generar una clase de cliente WCF mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
#### <a name="to-generate-a-wcf-client-class"></a>Para generar una clase de cliente WCF  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] el Explorador de soluciones, haga clic en el proyecto y, a continuación, haga clic en **Agregar referencia de servicio de adaptador**.  
  
2.  Después de la **Agregar referencia de servicio de adaptador** abre el cuadro de diálogo, siga los pasos descritos en [recuperación de metadatos para las operaciones de Siebel en Visual Studio](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md) para conectarse al sistema Siebel y examinar y buscar operaciones. Para crear una clase de cliente WCF para las operaciones que seleccionó, asegúrese de que **Client (Outbound operations)** está seleccionado en el **seleccione el tipo de contrato** lista desplegable (es decir, el valor predeterminado).  
  
3.  Después de seleccionar todas las operaciones que desea que tienen como destino, haga clic en **Aceptar** para generar la clase de cliente WCF.  
  
 El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] agrega dos archivos al proyecto:  
  
-   El archivo de código de cliente WCF. Este archivo contiene el generado WCF cliente clase y código auxiliar para las operaciones que seleccionó. La primera vez que ejecute la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] generará este archivo con el nombre predeterminado **SiebelBindingClient.cs** . Si se ejecuta de nuevo, se llamará el siguiente archivo se genera **SiebelBindingClient1.cs**.  El número de sufijo aumentarán en 1 para cada nuevo archivo que se generan.  También puede cambiar el prefijo predeterminado **SiebelBinding** escribiendo un prefijo diferente en el **prefijo de nombre de archivo** campo de la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] antes de seleccionar **Aceptar** a Genere el archivo.  
  
-   **App.config**. Este archivo contiene una configuración de enlace y las configuraciones de punto de conexión de cliente que se basan en las selecciones que realizó al configurar la conexión para el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Para obtener más información sobre el contenido del archivo app.config, vea [configurar un cliente de WCF para un sistema Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md).  
  
    > [!IMPORTANT]
    >  Al usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], si no especifica un valor para una propiedad de enlace de tipo cadena y cuyo valor predeterminado es null, a continuación, que enlaza la propiedad no estará disponible en el archivo app.config. Debe agregar manualmente la propiedad de enlace y su valor en el archivo app.config, si es necesario.  
  
## <a name="generating-a-wcf-client-class-by-using-svcutilexe"></a>Generar una clase de cliente WCF mediante svcutil.exe  
 Puede utilizar svcutil.exe para generar una clase de cliente WCF para la aplicación. Debe configurar svcutil.exe para usarlo con la [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]. Para obtener más información acerca de cómo configurar y usar svcutil.exe con la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], consulte [mediante la herramienta de utilidad de metadatos de ServiceModel con el adaptador de BizTalk para aplicaciones Siebel eBusiness](../../adapters-and-accelerators/adapter-siebel/use-the-servicemodel-metadata-utility-with-the-siebel-adapter.md).  
  
 Svcutil.exe genera la clase de cliente WCF en un archivo de salida con un nombre de archivo predeterminado de output.cs. Debe incluir manualmente este archivo en su [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] proyecto.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de Siebel mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)