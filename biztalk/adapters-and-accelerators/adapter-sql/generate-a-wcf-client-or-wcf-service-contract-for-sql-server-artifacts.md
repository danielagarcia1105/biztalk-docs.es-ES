---
title: Generar un cliente WCF o un contrato de servicio WCF para artefactos SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5fa7d8c0-8ee4-41e7-9394-d22e87e09391
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0930baa5ec89c500f15a5ae7a88ce36e71785c96
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013341"
---
# <a name="generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts"></a>Generar un cliente WCF o un contrato de servicio WCF para artefactos SQL Server
Puede usar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] generar una clase de cliente WCF de destino en operaciones seleccionadas en artefactos de SQL Server. También puede utilizar ServiceModel Metadata Utility Tool (svcutil.exe) para generar la clase de cliente WCF; Sin embargo, la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] expone la funcionalidad de ServiceModel Metadata Utility Tool a través de una interfaz estándar de Microsoft Windows. También proporciona funcionalidades de exploración y búsqueda que no están disponibles con la herramienta svcutil.exe y genera un archivo de configuración basado en las propiedades de enlace que seleccione al conectarse a la base de datos de SQL Server.  
  
## <a name="generating-a-wcf-client-class-by-using-the-add-adapter-service-reference-plug-in"></a>Generar una clase de cliente WCF mediante el Add Adapter Service Reference complemento  
 Realice los pasos siguientes para generar una clase de cliente WCF mediante el uso de la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
1. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] el Explorador de soluciones, haga clic en el proyecto y, a continuación, haga clic en **Add Adapter Service Reference**.  
  
2. Después de la **Add Adapter Service Reference** abre el cuadro de diálogo, siga los pasos descritos en [obtener metadatos para operaciones de SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md) para conectarse a SQL Server y para examinar y búsqueda de operaciones. Para crear una clase de cliente WCF para las operaciones que seleccionó, asegúrese de que **Client (Outbound operations)** está seleccionado en el **seleccione el tipo de contrato** lista desplegable. (Esto es el valor predeterminado).  
  
3. Después de seleccionar todas las operaciones que se desean tener como destino, haga clic en **Aceptar** para generar la clase de cliente WCF.  
  
   El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] agrega dos archivos al proyecto:  
  
- **El archivo de código de cliente WCF**. Este archivo contiene la generado WCF cliente clase y código auxiliar para las operaciones que seleccionó. La primera vez que ejecute la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], generará este archivo con el nombre predeterminado **SQLAdapterBindingClient.cs**. Si se ejecuta de nuevo, se llamará el siguiente archivo se genera **SQLAdapterBindingClient1.cs**.  El número de sufijo aumentarán en 1 para cada archivo nuevo que genera.  También puede cambiar el prefijo predeterminado **SQLBinding** escribiendo un prefijo diferente en el **prefijo de nombre de archivo** campo de la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] antes de seleccionar **Aceptar** a Genere el archivo.  
  
- **App.config**. Este archivo contiene una configuración de enlace y las configuraciones de punto de conexión de cliente que se basan en las selecciones realizadas al configurar la conexión para el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
  > [!IMPORTANT]
  >  Al usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], si no especifica un valor para una propiedad de enlace de tipo cadena y cuyo valor predeterminado es null, que enlaza la propiedad no estará disponible en el archivo app.config. Se deben agregar manualmente la propiedad de enlace y su valor en el archivo app.config, si es necesario.  
  
## <a name="generating-a-wcf-service-contract-by-using-the-add-adapter-service-reference-plug-in"></a>Generar un contrato de servicio WCF mediante el Add Adapter Service Reference complemento  
 Para las operaciones de entrada como sondear la base de datos de SQL Server o recibir notificaciones de la base de datos, el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejecuta una consulta especificada por la aplicación cliente (en el caso de sondeo) o una consulta se registra con SQL Server (en caso de notificación). En ambos escenarios, el adaptador envía el mensaje entrante de base de datos de SQL Server para el consumo. En tal caso, la aplicación que actúa como un servicio y el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] actúa como cliente. Por lo tanto, debe implementar un servicio WCF que puede recibir operaciones de entrada desde el adaptador. Para ello, usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar una interfaz de .NET que representa el contrato de servicio que aparece por el adaptador para las operaciones de entrada. Esta interfaz de .NET también se denomina un contrato de servicio WCF. A continuación, implemente esta interfaz para crear el servicio WCF que puede usar para recibir las operaciones de entrada.  
  
 Realice los pasos siguientes para generar un contrato de servicio WCF mediante el uso de la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
#### <a name="to-generate-a-wcf-service-contract-for-inbound-operations"></a>Para generar un contrato de servicio WCF para operaciones de entrada  
  
1. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] el Explorador de soluciones, haga clic en el proyecto y, a continuación, haga clic en **Add Adapter Service Reference**.  
  
2. Después de la **Add Adapter Service Reference** abre el cuadro de diálogo, siga los pasos descritos en [conectar con SQL Server en Visual Studio utilizando complemento Add Adapter Service Reference](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-add-adapter-service-reference.md) para conectarse a la base de datos de SQL Server.  
  
   > [!IMPORTANT]
   >  Si va a generar el contrato de servicio WCF para **TypedPolling** operación entrante, debe especificar el **InboundID** como parte de la conexión URI y **PollingStatement** propiedad de enlace.  
  
3. Después de haberse conectado a la base de datos de SQL Server, seleccione **(operaciones de entrada) de servicio** desde el **seleccione el tipo de contrato** lista desplegable.  
  
4. En el **seleccionar una categoría** cuadro, haga clic en el nodo raíz (**/**), seleccione la operación de entrada desde el **operaciones y categorías disponibles** cuadro y, a continuación, Haga clic en **agregar**.  
  
5. Para generar el contrato de servicio WCF para la operación de entrada, haga clic en **Aceptar**.  
  
   El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] agrega tres archivos al proyecto:  
  
- **SqlAdapterBindingInterface.cs**. Este archivo contiene WCF generado contrato (interfaz) y código auxiliar para la operación de entrada del servicio.  
  
- **SqlAdapterBindingService.cs**. Este archivo contiene una clase que implementa la interfaz definida en SqlAdapterBindingInterface.cs. Puede implementar la lógica de negocios que procesa los registros devueltos por la operación de entrada.  
  
- **App.config**. Este archivo contiene una configuración de enlace, comportamientos de punto de conexión y configuración del punto de conexión de servicio que se basan en las selecciones realizadas al configurar el enlace y conexión para el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
  > [!IMPORTANT]
  >  Al usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], si no especifica un valor para una propiedad de enlace de tipo cadena y cuyo valor predeterminado es null, que enlaza la propiedad no estará disponible en el archivo app.config. Se deben agregar manualmente la propiedad de enlace y su valor en el archivo app.config, si es necesario.  
  
## <a name="generating-a-wcf-client-class-by-using-svcutilexe"></a>Generar una clase de cliente WCF mediante svcutil.exe  
 Puede utilizar svcutil.exe para generar una clase de cliente WCF para la aplicación. Debe configurar svcutil.exe para usarlo con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
 Svcutil.exe genera la clase de cliente WCF en un archivo de salida con un nombre de archivo predeterminado de **output.cs**. Debe incluir manualmente este archivo en su [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] proyecto. Para obtener más información acerca de svcutil.exe, vea [ServiceModel Metadata Utility Tool (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx).
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de SQL con el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)