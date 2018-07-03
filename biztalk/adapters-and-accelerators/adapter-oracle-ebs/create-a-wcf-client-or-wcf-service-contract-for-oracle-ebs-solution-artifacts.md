---
title: Generar un cliente de WCF o un contrato de servicio WCF para artefactos de la solución de Oracle E-Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7ffd857-a177-423a-ae83-685d11b7aec6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9824e99014431c452f49d4a80e45efe4852c519f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986901"
---
# <a name="generate-a-wcf-client-or-a-wcf-service-contract-for-oracle-e-business-suite-solution-artifacts"></a>Generar un cliente de WCF o un contrato de servicio WCF para artefactos de la solución de Oracle E-Business Suite
Puede usar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar una clase de cliente WCF o un contrato de servicio WCF (interfaz) dirigido a las operaciones seleccionadas en artefactos de Oracle E-Business Suite. También puede usar el contrato de servicio WCF; o ServiceModel Metadata Utility Tool (svcutil.exe) para generar la clase de cliente WCF Sin embargo, la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] expone la funcionalidad de ServiceModel Metadata Utility Tool a través de una interfaz estándar de Microsoft Windows. También proporciona funcionalidades de exploración y búsqueda que no están disponibles con la herramienta svcutil.exe, y genera un archivo de configuración basado en las propiedades de enlace que seleccione al conectarse a Oracle E-Business Suite.  
  
## <a name="generating-a-client-class-by-using-the-add-adapter-service-reference-plug-in"></a>Generar una clase de cliente mediante el Add Adapter Service Reference complemento  
 Realice los pasos siguientes para generar una clase de cliente WCF mediante el uso de la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
#### <a name="to-generate-a-wcf-client-class"></a>Para generar una clase de cliente WCF  
  
1. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] el Explorador de soluciones, haga clic en el proyecto y, a continuación, haga clic en **Add Adapter Service Reference**.  
  
2. Después de la **Add Adapter Service Reference** abre el cuadro de diálogo, siga los pasos descritos en [recuperación de metadatos para las operaciones de Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md) para conectarse a Oracle E-Business Suite y Examinar y buscar las operaciones. Para crear una clase de cliente WCF para las operaciones que seleccionó, asegúrese de que **Client (Outbound operations)** está seleccionado en el **seleccione el tipo de contrato** lista desplegable (es decir, el valor predeterminado).  
  
3. Después de seleccionar todas las operaciones que se desean tener como destino, haga clic en **Aceptar** para generar la clase de cliente WCF.  
  
   El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] agrega dos archivos al proyecto:  
  
- **OracleEBSBindingClient.cs**. Este archivo contiene la generado WCF cliente clase y código auxiliar para las operaciones que seleccionó.  
  
- **App.config**. Este archivo contiene una configuración de enlace y las configuraciones de punto de conexión de cliente. Estas configuraciones se basan en las selecciones realizadas al configurar el enlace y conexión para el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
  > [!IMPORTANT]
  >  Al usar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], si no especifica un valor para una propiedad de enlace de tipo cadena y cuyo valor predeterminado es null, que enlaza la propiedad no estará disponible en el archivo app.config. Se deben agregar manualmente la propiedad de enlace y su valor en el archivo app.config, si es necesario.  
  
## <a name="generating-a-wcf-service-contract-by-using-the-add-adapter-service-reference-plug-in"></a>Generar un contrato de servicio WCF mediante el Add Adapter Service Reference complemento  
 El adaptador expone las operaciones de entrada para habilitar Oracle E-Business Suite enviar mensajes a un cliente del adaptador. Para estas operaciones debe generar un contrato de servicio WCF. Esta sección proporciona información sobre cómo generar un contrato de servicio para las operaciones de entrada expuestos por el adaptador.  
  
 Realice los pasos siguientes para generar un contrato de servicio WCF mediante el uso de la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
#### <a name="to-generate-a-wcf-service-contract-for-inbound-operations"></a>Para generar un contrato de servicio WCF para operaciones de entrada  
  
1. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] el Explorador de soluciones, haga clic en el proyecto y, a continuación, haga clic en **Add Adapter Service Reference**.  
  
2. Después de la **Add Adapter Service Reference** abre el cuadro de diálogo, siga los pasos descritos en [recuperación de metadatos para las operaciones de Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md) para conectarse a Oracle E-Business Suite. Hay varias propiedades de enlace y una propiedad de identificador URI que desee establecer al conectarse a Oracle E-Business Suite.  
  
3. Después de haberse conectado a Oracle E-Business Suite, seleccione **(operaciones de entrada) de servicio** desde el **seleccione el tipo de contrato** lista desplegable.  
  
4. En el **seleccionar una categoría** cuadro, vaya a la operación de entrada para el que desea generar el contrato de servicio. Por ejemplo, para **notificación** operación, haga clic en el nodo raíz (**/**), seleccione **notificación** desde el **categorías disponibles y las operaciones** cuadro y, a continuación, haga clic en **agregar**. Para obtener instrucciones sobre cómo buscar operaciones entrantes, vea [exploración, búsqueda y recuperación de metadatos para las operaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md).  
  
5. Para generar el contrato de servicio WCF para la operación, haga clic en **Aceptar**.  
  
   El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] agrega tres archivos al proyecto:  
  
- **OracleEBSBindingInterface.cs**. Este archivo contiene WCF generado contrato (interfaz) y código auxiliar para la operación de entrada del servicio.  
  
- **OracleEBSBindingService.cs**. Este archivo contiene una clase que implementa la interfaz definida en OracleDBBindingInterface.cs. Puede implementar la lógica de negocios que procesa los registros devueltos por la operación de entrada.  
  
- **App.config**. Este archivo contiene una configuración de enlace, comportamientos de punto de conexión y configuración del punto de conexión de servicio que se basan en las selecciones realizadas al configurar el enlace y conexión para el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
  > [!IMPORTANT]
  >  Al usar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], si no especifica un valor para una propiedad de enlace de tipo cadena y cuyo valor predeterminado es null, que enlaza la propiedad no estará disponible en el archivo app.config. Se deben agregar manualmente la propiedad de enlace y su valor en el archivo app.config, si es necesario.  
  
## <a name="using-svcutilexe-to-generate-a-wcf-client-class-or-a-wcf-service-contract"></a>Utilizar svcutil.exe para generar una clase de cliente WCF o un contrato de servicio WCF  
 Puede utilizar svcutil.exe para generar una clase de cliente WCF o una interfaz de servicio WCF para la aplicación. Debe configurar svcutil.exe para usarlo con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
 Svcutil.exe genera la clase de cliente WCF o el contrato de servicio WCF en un archivo de salida. El nombre de archivo predeterminado es output.cs. Debe incluir manualmente este archivo en su [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] proyecto. Para obtener más información acerca de svcutil.exe, vea [ http://go.microsoft.com/fwlink/?LinkId=139432 ](http://go.microsoft.com/fwlink/?LinkId=139432).