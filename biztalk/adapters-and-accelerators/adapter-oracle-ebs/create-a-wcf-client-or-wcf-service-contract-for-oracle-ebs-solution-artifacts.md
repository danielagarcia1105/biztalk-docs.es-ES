---
title: "Generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución de Oracle E-Business Suite | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7ffd857-a177-423a-ae83-685d11b7aec6
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc7fb7dc0df1c2cbf4c4f8b1118cba07df6c7231
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="generate-a-wcf-client-or-a-wcf-service-contract-for-oracle-e-business-suite-solution-artifacts"></a>Generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución de Oracle E-Business Suite
Puede usar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar una clase de cliente WCF o un contrato de servicio WCF (interfaz) destinada a operaciones seleccionadas en artefactos de Oracle E-Business Suite. También puede usar el contrato de servicio WCF; o ServiceModel Metadata Utility Tool (svcutil.exe) para generar la clase de cliente WCF Sin embargo, la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] expone la funcionalidad de la herramienta de utilidad de metadatos de ServiceModel mediante una interfaz estándar de Microsoft Windows. También proporciona capacidades de exploración y búsqueda que no están disponibles con la herramienta svcutil.exe, y genera un archivo de configuración basado en las propiedades de enlace que seleccione al conectarse a Oracle E-Business Suite.  
  
## <a name="generating-a-client-class-by-using-the-add-adapter-service-reference-plug-in"></a>Generar una clase de cliente mediante el Agregar referencia de servicio de adaptador complemento  
 Realice los pasos siguientes para generar una clase de cliente WCF mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
#### <a name="to-generate-a-wcf-client-class"></a>Para generar una clase de cliente WCF  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] el Explorador de soluciones, haga clic en el proyecto y, a continuación, haga clic en **Agregar referencia de servicio de adaptador**.  
  
2.  Después de la **Agregar referencia de servicio de adaptador** abre el cuadro de diálogo, siga los pasos descritos en [recuperación de metadatos para las operaciones de Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md) para conectarse a Oracle E-Business Suite y Examinar y buscar las operaciones. Para crear una clase de cliente WCF para las operaciones que seleccionó, asegúrese de que **Client (Outbound operations)** está seleccionado en el **seleccione el tipo de contrato** lista desplegable (es decir, el valor predeterminado).  
  
3.  Después de seleccionar todas las operaciones que desea que tienen como destino, haga clic en **Aceptar** para generar la clase de cliente WCF.  
  
 El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] agrega dos archivos al proyecto:  
  
-   **OracleEBSBindingClient.cs**. Este archivo contiene el generado WCF cliente clase y código auxiliar para las operaciones que seleccionó.  
  
-   **App.config**. Este archivo contiene una configuración de enlace y las configuraciones de punto de conexión de cliente. Estas configuraciones se basan en las selecciones que realizó al configurar el enlace y la conexión para el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
    > [!IMPORTANT]
    >  Al usar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], si no especifica un valor para una propiedad de enlace de tipo cadena y cuyo valor predeterminado es null, a continuación, que enlaza la propiedad no estará disponible en el archivo app.config. Debe agregar manualmente la propiedad de enlace y su valor en el archivo app.config, si es necesario.  
  
## <a name="generating-a-wcf-service-contract-by-using-the-add-adapter-service-reference-plug-in"></a>Generar un contrato de servicio WCF mediante el Agregar referencia de servicio de adaptador complemento  
 El adaptador expone las operaciones de entrada para habilitar Oracle E-Business Suite enviar mensajes a un cliente de adaptador. Para estas operaciones debe generar un contrato de servicio WCF. Esta sección proporciona información sobre cómo generar un contrato de servicio para operaciones de entrada expuestos por el adaptador.  
  
 Realice los pasos siguientes para generar un contrato de servicio WCF mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
#### <a name="to-generate-a-wcf-service-contract-for-inbound-operations"></a>Para generar un contrato de servicio WCF para operaciones de entrada  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] el Explorador de soluciones, haga clic en el proyecto y, a continuación, haga clic en **Agregar referencia de servicio de adaptador**.  
  
2.  Después de la **Agregar referencia de servicio de adaptador** abre el cuadro de diálogo, siga los pasos descritos en [recuperación de metadatos para las operaciones de Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md) para conectarse a Oracle E-Business Suite. Hay varias propiedades de enlace y una propiedad URI que se puede establecer cuando se conecta a Oracle E-Business Suite.  
  
3.  Después de haberse conectado a Oracle E-Business Suite, seleccione **(operaciones de entrada) de servicio** desde el **seleccione el tipo de contrato** lista desplegable.  
  
4.  En el **seleccione una categoría de** cuadro, vaya a la operación de entrada para el que desea generar el contrato de servicio. Por ejemplo, para **notificación** operación, haga clic en el nodo raíz (**/**), seleccione **notificación** desde el **categorías disponibles y operaciones** cuadro y, a continuación, haga clic en **agregar**. Para obtener instrucciones sobre cómo buscar operaciones entrantes, consulte [exploración, búsqueda y recuperación de metadatos para las operaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md).  
  
5.  Para generar el contrato de servicio WCF para la operación, haga clic en **Aceptar**.  
  
 El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] agrega tres archivos al proyecto:  
  
-   **OracleEBSBindingInterface.cs**. Este archivo contiene el WCF generado contrato (interfaz) y código auxiliar para la operación de entrada de servicio.  
  
-   **OracleEBSBindingService.cs**. Este archivo contiene una clase que implementa la interfaz definida en OracleDBBindingInterface.cs. Puede implementar la lógica de negocios que procesa los registros devueltos por la operación de entrada.  
  
-   **App.config**. Este archivo contiene una configuración de enlace, comportamientos de punto de conexión y configuración de extremo de servicio que se basan en las selecciones que realizó al configurar el enlace y la conexión para el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
    > [!IMPORTANT]
    >  Al usar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], si no especifica un valor para una propiedad de enlace de tipo cadena y cuyo valor predeterminado es null, a continuación, que enlaza la propiedad no estará disponible en el archivo app.config. Debe agregar manualmente la propiedad de enlace y su valor en el archivo app.config, si es necesario.  
  
## <a name="using-svcutilexe-to-generate-a-wcf-client-class-or-a-wcf-service-contract"></a>Utilizar svcutil.exe para generar una clase de cliente WCF o un contrato de servicio WCF  
 Puede utilizar svcutil.exe para generar una clase de cliente WCF o una interfaz de servicio WCF para la aplicación. Debe configurar svcutil.exe para usarlo con la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
 Svcutil.exe genera la clase de cliente WCF o el contrato de servicio WCF en un archivo de salida. El nombre de archivo predeterminado es output.cs. Debe incluir manualmente este archivo en su [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] proyecto. Para obtener más información acerca de svcutil.exe, vea [http://go.microsoft.com/fwlink/?LinkId=139432](http://go.microsoft.com/fwlink/?LinkId=139432).