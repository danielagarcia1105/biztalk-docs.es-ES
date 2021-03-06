---
title: Generar un cliente de WCF o un contrato de servicio WCF para artefactos de la solución de base de datos de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model programming, creating a proxy
- how to, create a proxy
- creating a proxy
- proxy programming, creating a proxy
ms.assetid: 3e832ae9-e253-4476-9f25-8cf0de12f469
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1e042fb8a60953996f4651d4a4397f75a264e32
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967509"
---
# <a name="generate-a-wcf-client-or-a-wcf-service-contract-for-oracle-database-solution-artifacts"></a>Generar un cliente de WCF o un contrato de servicio WCF para artefactos de la solución de base de datos de Oracle
Puede usar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar una clase de cliente WCF o un contrato de servicio WCF (interfaz) dirigido a las operaciones seleccionadas en artefactos de la base de datos de Oracle. También puede usar el contrato de servicio WCF; o ServiceModel Metadata Utility Tool (svcutil.exe) para generar la clase de cliente WCF Sin embargo, la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] expone la funcionalidad de ServiceModel Metadata Utility Tool a través de una interfaz estándar de Microsoft Windows. También proporciona funcionalidades de exploración y búsqueda que no están disponibles con la herramienta svcutil.exe, y genera un archivo de configuración basado en las propiedades de enlace que seleccione al conectarse a la base de datos de Oracle.  
  
## <a name="generating-a-client-class-by-using-the-add-adapter-service-reference-plug-in"></a>Generar una clase de cliente mediante el Add Adapter Service Reference complemento  
 Realice los pasos siguientes para generar una clase de cliente WCF mediante el uso de la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
#### <a name="to-generate-a-wcf-client-class"></a>Para generar una clase de cliente WCF  
  
1. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] el Explorador de soluciones, haga clic en el proyecto y, a continuación, haga clic en **Add Adapter Service Reference**.  
  
2. Después de la **Add Adapter Service Reference** abre el cuadro de diálogo, siga los pasos descritos en [recuperar metadatos para operaciones de Oracle en Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md) para conectarse a la base de datos de Oracle y examinar y buscar operaciones. Para crear una clase de cliente WCF para las operaciones que seleccionó, asegúrese de que **Client (Outbound operations)** está seleccionado en el **seleccione el tipo de contrato** lista desplegable (es decir, el valor predeterminado).  
  
3. Después de seleccionar todas las operaciones que se desean tener como destino, haga clic en **Aceptar** para generar la clase de cliente WCF.  
  
   El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] agrega dos archivos al proyecto:  
  
- **OracleDBBindingClient.cs**. Este archivo contiene la generado WCF cliente clase y código auxiliar para las operaciones que seleccionó.  
  
- **App.config**. Este archivo contiene una configuración de enlace y las configuraciones de punto de conexión de cliente. Estas configuraciones se basan en las selecciones realizadas al configurar el enlace y conexión para el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
  > [!IMPORTANT]
  >  Al usar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], si no especifica un valor para una propiedad de enlace de tipo cadena y cuyo valor predeterminado es null, que enlaza la propiedad no estará disponible en el archivo app.config. Se deben agregar manualmente la propiedad de enlace y su valor en el archivo app.config, si es necesario.  
  
## <a name="generating-a-wcf-service-contract-by-using-the-add-adapter-service-reference-plug-in"></a>Generar un contrato de servicio WCF mediante el Add Adapter Service Reference complemento  
 El adaptador expone las operaciones de entrada para habilitar la base de datos de Oracle enviar mensajes a un cliente del adaptador. Para estas operaciones debe generar un contrato de servicio WCF. Por ejemplo, el adaptador expone una operación POLLINGSTMT entrante para sondear la base de datos de Oracle. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] ejecuta la consulta especificada por el **PollingStatement** propiedad y envía el conjunto de resultados a la aplicación que lo consume en un mensaje POLLINGSTMT de enlace. En este escenario, la aplicación que actúa como un servicio y el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] actúa como cliente. Por lo tanto, debe implementar un servicio WCF que puede recibir la operación POLLINGSTMT desde el adaptador. Para ello, usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar una interfaz de .NET que representa el contrato de servicio que aparece por el adaptador para la operación POLLINGSTMT. Esta interfaz de .NET también se denomina un contrato de servicio WCF. A continuación, implemente esta interfaz para crear el servicio WCF que puede usar para recibir la operación POLLINGSTMT.  
  
 Esta sección proporciona información sobre cómo generar un contrato de servicio WCF mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para operaciones de entrada expuestas por el adaptador.  
  
#### <a name="to-generate-a-wcf-service-contract-for-inbound-operations"></a>Para generar un contrato de servicio WCF para operaciones de entrada  
  
1. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] el Explorador de soluciones, haga clic en el proyecto y, a continuación, haga clic en **Add Adapter Service Reference**.  
  
2. Después de la **Add Adapter Service Reference** abre el cuadro de diálogo, siga los pasos descritos en [recuperar metadatos para operaciones de Oracle en Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md) para conectarse a la base de datos de Oracle. Hay varias propiedades de enlace y una propiedad de identificador URI que desea establecer cuando se conecta a la base de datos de Oracle para operaciones de entrada. Por ejemplo, para la operación de sondeo entrante (**POLLINGSTMT**), debe especificar el **PollingStatement** enlaza la propiedad cuando se configura la conexión a la base de datos de Oracle. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] la instrucción SELECT de SQL especificada en esta propiedad se utiliza para generar la clase que representa el conjunto de resultados devuelto por la operación POLLINGSTMT.  
  
3. Después de haberse conectado a la base de datos de Oracle, seleccione **(operaciones de entrada) de servicio** desde el **seleccione el tipo de contrato** lista desplegable.  
  
4. En el **seleccionar una categoría** cuadro, haga clic en el nodo raíz (**/**) y vaya a la operación para la que desea generar el contrato de servicio. Por ejemplo, para la operación de sondeo, seleccione **POLLINGSTMT** desde el **operaciones y categorías disponibles** cuadro y, a continuación, haga clic en **agregar**.  
  
5. Para generar el contrato de servicio WCF para la operación POLLINGSTMT, haga clic en **Aceptar**.  
  
   El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] agrega tres archivos al proyecto:  
  
- **OracleDBBindingInterface.cs**. Este archivo contiene WCF generado contrato (interfaz) y código auxiliar para la operación POLLINGSTMT del servicio.  
  
- **OracleDBBindingService.cs**. Este archivo contiene una clase que implementa la interfaz definida en OracleDBBindingInterface.cs. Puede implementar la lógica de negocios que procesa los registros devueltos por la consulta de sondeo en el método POLLINGSTMT en esta clase.  
  
- **App.config**. Este archivo contiene una configuración de enlace, comportamientos de punto de conexión y configuración del punto de conexión de servicio que se basan en las selecciones realizadas al configurar el enlace y conexión para el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
  > [!IMPORTANT]
  >  Al usar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], si no especifica un valor para una propiedad de enlace de tipo cadena y cuyo valor predeterminado es null, que enlaza la propiedad no estará disponible en el archivo app.config. Se deben agregar manualmente la propiedad de enlace y su valor en el archivo app.config, si es necesario.  
  
## <a name="using-svcutilexe-to-generate-a-wcf-client-class-or-a-wcf-service-contract"></a>Utilizar svcutil.exe para generar una clase de cliente WCF o un contrato de servicio WCF  
 Puede utilizar svcutil.exe para generar una clase de cliente WCF o una interfaz de servicio WCF para la aplicación. Debe configurar svcutil.exe para usarlo con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Para obtener más información sobre cómo configurar y usar svcutil.exe con la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [uso ServiceModel Metadata Utility Tool con el adaptador de BizTalk para Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/use-the-servicemodel-metadata-utility-with-the-oracle-db-adapter-in-biztalk.md).  
  
 Svcutil.exe genera la clase de cliente WCF o el contrato de servicio WCF en un archivo de salida. El nombre de archivo predeterminado es output.cs. Debe incluir manualmente este archivo en su [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] proyecto.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)   
 [Realizar básicas Insert, Update, Delete y las operaciones Select de SQL mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sql/insert-update-delete-or-select-operations-in-sql-using-the-wcf-service-model.md)