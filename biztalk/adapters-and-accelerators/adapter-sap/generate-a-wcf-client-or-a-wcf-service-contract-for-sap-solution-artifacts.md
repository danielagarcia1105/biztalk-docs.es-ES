---
title: "Generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución SAP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ff01e2b0-6480-427a-bc6d-6169e7d6e256
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 035f1263922a0c455662139ca112794e920e3848
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts"></a>Generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución SAP
Puede usar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar una clase de cliente WCF o un contrato de servicio WCF (interfaz) destinada a operaciones seleccionadas en artefactos SAP. También puede usar el contrato de servicio WCF; o ServiceModel Metadata Utility Tool (svcutil.exe) para generar la clase de cliente WCF Sin embargo, la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] expone la funcionalidad de la herramienta de utilidad de metadatos de ServiceModel mediante una interfaz estándar de Microsoft Windows. También proporciona capacidades de exploración y búsqueda que no están disponibles con la herramienta svcutil.exe y genera un archivo de configuración basado en las propiedades de enlace que se selecciona cuando se conecta al sistema SAP.  
  
## <a name="generating-a-client-class-by-using-the-add-adapter-service-reference-plug-in"></a>Generar una clase de cliente mediante el Agregar referencia de servicio de adaptador complemento  
 Realice los pasos siguientes para generar una clase de cliente WCF mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
#### <a name="to-generate-a-wcf-client-class"></a>Para generar una clase de cliente WCF  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] el Explorador de soluciones, haga clic en el proyecto y, a continuación, haga clic en **Agregar referencia de servicio de adaptador**.  
  
2.  Después de la **Agregar referencia de servicio de adaptador** abre el cuadro de diálogo, siga los pasos descritos en [obtener metadatos para operaciones de SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md) para conectarse al sistema SAP y examinar y buscar para las operaciones. Para crear una clase de cliente WCF para las operaciones que seleccionó, asegúrese de que **Client (Outbound operations)** está seleccionado en el **seleccione el tipo de contrato** lista desplegable (es decir, el valor predeterminado).  
  
3.  Después de seleccionar todas las operaciones que desea que tienen como destino, haga clic en **Aceptar** para generar la clase de cliente WCF.  
  
 El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] agrega dos archivos al proyecto:  
  
-   **SAPBindingClient.cs**. Este archivo contiene el generado WCF cliente clase y código auxiliar para las operaciones que seleccionó.  
  
-   **App.config**. Este archivo contiene una configuración de enlace y las configuraciones de punto de conexión de cliente. La configuración se basa en las selecciones que realizó al configurar el enlace y la conexión para el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
    > [!IMPORTANT]
    >  Al usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], si no especifica un valor para una propiedad de enlace de tipo cadena y cuyo valor predeterminado es null, a continuación, que enlaza la propiedad no estará disponible en el archivo app.config. Debe agregar manualmente la propiedad de enlace y su valor en el archivo app.config, si es necesario.  
  
## <a name="generating-a-wcf-service-contract-by-using-the-add-adapter-service-reference-plug-in"></a>Generar un contrato de servicio WCF mediante el Agregar referencia de servicio de adaptador complemento  
 Cuando se usa el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para recibir IDOC y RFC, tRFCs desde el sistema SAP, el código actúa como un servicio en el adaptador. Es decir, el adaptador recibe del artefacto correspondiente desde el sistema SAP y, a continuación, invoca una operación (entrada) en el código para entregar el artefacto a la aplicación.  
  
 Por lo tanto, debe implementar un servicio WCF que puede recibir esta operación entrante desde el adaptador. Para ello, use el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar una interfaz de .NET que representa el contrato de servicio que aparece por el adaptador para la operación. Esta interfaz .NET también se denomina un contrato de servicio WCF. El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] también genera una clase que contiene una implementación auxiliar del servicio WCF. A continuación, implemente esta interfaz para crear el servicio WCF que puede usar para la operación de recepción.  
  
 Realice los pasos siguientes para generar un contrato de servicio WCF mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
#### <a name="to-generate-a-wcf-service-contract"></a>Para generar un contrato de servicio WCF  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] el Explorador de soluciones, haga clic en el proyecto y, a continuación, haga clic en **Agregar referencia de servicio de adaptador**.  
  
2.  Después de la **Agregar referencia de servicio de adaptador** abre el cuadro de diálogo, siga los pasos descritos en [obtener metadatos para operaciones de SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md) para conectarse al sistema SAP y examinar y buscar para las operaciones. Para crear un contrato de servicio WCF para las operaciones que seleccionó, asegúrese de que **(operaciones de entrada) de servicio** está seleccionado en el **seleccione el tipo de contrato** lista desplegable.  
  
3.  Después de seleccionar todas las operaciones que desea que tienen como destino, haga clic en **Aceptar** para generar el contrato de servicio WCF.  
  
 El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] agrega tres archivos al proyecto:  
  
-   **SAPBindingInterface.cs**. Este archivo contiene el WCF generado servicio contrato (interfaz) y código auxiliar para las operaciones que seleccionó.  
  
-   **SAPBindingService.cs**. Este archivo contiene una clase auxiliar de servicio WCF que implementa la interfaz definida en SAPBindingInterface.cs. Puede implementar la lógica de negocios que procesa la RFC, tRFC o IDOC directamente en los métodos de esta clase.  
  
-   **App.config**. Este archivo contiene una configuración de enlace, comportamientos de punto de conexión y configuración de extremo de servicio que se basan en las selecciones que realizó al configurar el enlace y la conexión para el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
    > [!IMPORTANT]
    >  Al usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], si no especifica un valor para una propiedad de enlace de tipo cadena y cuyo valor predeterminado es null, a continuación, que enlaza la propiedad no estará disponible en el archivo app.config. Debe agregar manualmente la propiedad de enlace y su valor en el archivo app.config, si es necesario.  
  
> [!NOTE]
>  No es necesario especificar parámetros de servidor RFC al configurar el URI de conexión para el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar el contrato de servicio WCF. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] recupera los metadatos desde el sistema SAP a través de una conexión de cliente.  
  
## <a name="generate-a-wcf-client-class-or-a-wcf-service-contract-by-using-svcutilexe"></a>Generar una clase de cliente WCF o un contrato de servicio WCF mediante svcutil.exe  
 Puede utilizar svcutil.exe para generar una clase de cliente WCF o un contrato de servicio WCF para la aplicación. Debe configurar svcutil.exe para usarlo con la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Para obtener más información acerca de cómo configurar y usar svcutil.exe con la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], consulte [mediante la herramienta de utilidad de metadatos de ServiceModel con el adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-servicemodel-metadata-utility-with-the-sap-adapter-in-biztalk.md).  
  
 Svcutil.exe genera la clase de cliente WCF o el contrato de servicio WCF en un archivo de salida. El nombre de archivo predeterminado es output.cs. Debe incluir manualmente este archivo en su [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] proyecto.  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de SAP mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)