---
title: Generar un cliente de WCF o un contrato de servicio WCF de artefactos SQL Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5fa7d8c0-8ee4-41e7-9394-d22e87e09391
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f961c3648e153847f5ac259c9902da5589b1486d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts"></a>Generar un cliente de WCF o un contrato de servicio WCF de artefactos SQL Server
Puede usar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] generar una clase de cliente WCF destinada a operaciones seleccionadas en artefactos de SQL Server. También puede usar la herramienta de utilidad de metadatos de ServiceModel (svcutil.exe) para generar la clase de cliente WCF; Sin embargo, la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] expone la funcionalidad de la herramienta de utilidad de metadatos de ServiceModel mediante una interfaz estándar de Microsoft Windows. También proporciona capacidades de exploración y búsqueda que no están disponibles con la herramienta svcutil.exe y genera un archivo de configuración basado en las propiedades de enlace que se selecciona cuando se conecta a la base de datos de SQL Server.  
  
## <a name="generating-a-wcf-client-class-by-using-the-add-adapter-service-reference-plug-in"></a>Generar una clase de cliente WCF mediante el Agregar referencia de servicio de adaptador complemento  
 Realice los pasos siguientes para generar una clase de cliente WCF mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] el Explorador de soluciones, haga clic en el proyecto y, a continuación, haga clic en **Agregar referencia de servicio de adaptador**.  
  
2.  Después de la **Agregar referencia de servicio de adaptador** abre el cuadro de diálogo, siga los pasos descritos en [obtener los metadatos de las operaciones de SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md) para conectarse a SQL Server y para examinar y búsqueda de operaciones. Para crear una clase de cliente WCF para las operaciones que seleccionó, asegúrese de que **Client (Outbound operations)** está seleccionado en el **seleccione el tipo de contrato** lista desplegable. (Este es el valor predeterminado).  
  
3.  Después de seleccionar todas las operaciones que desea que tienen como destino, haga clic en **Aceptar** para generar la clase de cliente WCF.  
  
 El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] agrega dos archivos al proyecto:  
  
-   **El archivo de código de cliente WCF**. Este archivo contiene el generado WCF cliente clase y código auxiliar para las operaciones que seleccionó. La primera vez que ejecute la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], generará este archivo con el nombre predeterminado **SQLAdapterBindingClient.cs**. Si se ejecuta de nuevo, se llamará el siguiente archivo se genera **SQLAdapterBindingClient1.cs**.  El número de sufijo aumentarán en 1 para cada nuevo archivo que se generan.  También puede cambiar el prefijo predeterminado **SQLBinding** escribiendo un prefijo diferente en el **prefijo de nombre de archivo** campo de la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] antes de seleccionar **Aceptar** a Genere el archivo.  
  
-   **App.config**. Este archivo contiene una configuración de enlace y las configuraciones de punto de conexión de cliente que se basan en las selecciones que realizó al configurar la conexión para el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
    > [!IMPORTANT]
    >  Al usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], si no especifica un valor para una propiedad de enlace de tipo cadena y cuyo valor predeterminado es null, a continuación, que enlaza la propiedad no estará disponible en el archivo app.config. Debe agregar manualmente la propiedad de enlace y su valor en el archivo app.config, si es necesario.  
  
## <a name="generating-a-wcf-service-contract-by-using-the-add-adapter-service-reference-plug-in"></a>Generar un contrato de servicio WCF mediante el Agregar referencia de servicio de adaptador complemento  
 Operaciones de entrada como sondear la base de datos de SQL Server para recibir notificaciones de la base de datos, la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejecuta una consulta especificada por la aplicación de cliente (en el caso de sondeo) o registra una consulta con SQL Server (en caso de notificación). En ambos escenarios, el adaptador envía el mensaje entrante de base de datos de SQL Server para el consumo. En tal caso, la aplicación que consume actúa como un servicio y el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] actúa como el cliente. Por lo tanto, debe implementar un servicio WCF que puede recibir operaciones entrantes desde el adaptador. Para ello, use el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar una interfaz de .NET que representa el contrato de servicio que se obtenidas por el adaptador para las operaciones de entrada. Esta interfaz .NET también se denomina un contrato de servicio WCF. A continuación, implemente esta interfaz para crear el servicio WCF que puede usar para recibir las operaciones de entrada.  
  
 Realice los pasos siguientes para generar un contrato de servicio WCF mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
#### <a name="to-generate-a-wcf-service-contract-for-inbound-operations"></a>Para generar un contrato de servicio WCF para operaciones de entrada  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] el Explorador de soluciones, haga clic en el proyecto y, a continuación, haga clic en **Agregar referencia de servicio de adaptador**.  
  
2.  Después de la **Agregar referencia de servicio de adaptador** abre el cuadro de diálogo, siga los pasos descritos en [conectar con SQL Server en Visual Studio utilizando Agregar adaptador servicio referencia complemento](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-add-adapter-service-reference.md) para conectarse a la base de datos de SQL Server.  
  
    > [!IMPORTANT]
    >  Si va a generar el contrato de servicio WCF para **TypedPolling** operación entrante, debe especificar el **InboundID** como parte del URI de conexión y **PollingStatement** propiedad de enlace.  
  
3.  Después de haberse conectado a la base de datos de SQL Server, seleccione **(operaciones de entrada) de servicio** desde el **seleccione el tipo de contrato** lista desplegable.  
  
4.  En el **seleccione una categoría de** cuadro, haga clic en el nodo raíz (**/**), seleccione la operación de entrada desde el **categorías y operaciones disponibles** cuadro y, a continuación, Haga clic en **agregar**.  
  
5.  Para generar el contrato de servicio WCF para la operación de entrada, haga clic en **Aceptar**.  
  
 El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] agrega tres archivos al proyecto:  
  
-   **SqlAdapterBindingInterface.cs**. Este archivo contiene el WCF generado contrato (interfaz) y código auxiliar para la operación de entrada de servicio.  
  
-   **SqlAdapterBindingService.cs**. Este archivo contiene una clase que implementa la interfaz definida en SqlAdapterBindingInterface.cs. Puede implementar la lógica de negocios que procesa los registros devueltos por la operación de entrada.  
  
-   **App.config**. Este archivo contiene una configuración de enlace, comportamientos de punto de conexión y configuración de extremo de servicio que se basan en las selecciones que realizó al configurar el enlace y la conexión para el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
    > [!IMPORTANT]
    >  Al usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], si no especifica un valor para una propiedad de enlace de tipo cadena y cuyo valor predeterminado es null, a continuación, que enlaza la propiedad no estará disponible en el archivo app.config. Debe agregar manualmente la propiedad de enlace y su valor en el archivo app.config, si es necesario.  
  
## <a name="generating-a-wcf-client-class-by-using-svcutilexe"></a>Generar una clase de cliente WCF mediante svcutil.exe  
 Puede utilizar svcutil.exe para generar una clase de cliente WCF para la aplicación. Debe configurar svcutil.exe para usarlo con la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
 Svcutil.exe genera la clase de cliente WCF en un archivo de salida con un nombre de archivo predeterminado de **output.cs**. Debe incluir manualmente este archivo en su [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] proyecto. Para obtener más información acerca de svcutil.exe, vea [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx).
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de SQL con el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)