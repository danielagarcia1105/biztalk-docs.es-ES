---
title: Conectarse a SQL Server en Visual Studio mediante Agregar referencia de servicio de adaptador complemento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fc3b824-d20b-4531-81f3-89b4a1ff3216
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 506d0cc1d4f4fca94b71aef3e6d4855a2afb845b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226540"
---
# <a name="connect-to-sql-server-in-visual-studio-using-add-adapter-service-reference-plug-in"></a>Conectarse a SQL Server en Visual Studio mediante Agregar referencia de servicio de adaptador complemento
Para conectarse a SQL Server mediante la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en una solución de programación. NET, debe utilizar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]. Este tema proporciona instrucciones sobre cómo usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
## <a name="connecting-to-sql-server-using-add-adapter-service-reference-plug-in"></a>Conectar a SQL Server mediante Agregar referencia de servicio de adaptador complemento  
 Realice los pasos siguientes para conectarse a SQL Server mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
#### <a name="to-connect-to-sql-server"></a>Para conectarse a SQL Server  
  
1.  Para conectarse mediante la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] en una solución de programación:  
  
    1.  Crear un proyecto en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].  
  
    2.  Haga clic en el proyecto en el Explorador de soluciones y, a continuación, haga clic en **Agregar referencia de servicio de adaptador**. Se abrirá [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
2.  Desde el **selecciona un enlace** lista desplegable, seleccione **sqlBinding**y, a continuación, haga clic en **configurar**.  
  
3.  En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** ficha y desde el **tipo de credencial de cliente** lista desplegable, realice una de las siguientes acciones:  
  
    > [!NOTE]
    >  Si se conecta a SQL Server mediante autenticación de Windows, el usuario de Windows con la que ha iniciado sesión debe agregarse a SQL Server como se describe en [conectar con SQL Server mediante la autenticación de Windows con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).  
  
    |Haga clic en|Para|  
    |----------------|----------------|  
    |**Ninguno**|Conectarse a SQL Server mediante la autenticación de Windows.|  
    |**Windows**|Conectarse a SQL Server mediante la autenticación de Windows.|  
    |**Nombre de usuario**|Especifique un nombre de usuario y una contraseña para conectarse a SQL Server especificando credenciales para un usuario definido en la base de datos de SQL Server. Tenga en cuenta que el nombre de usuario y la contraseña distinguen entre mayúsculas y minúsculas. **Nota:** si deja la **nombre de usuario** y **contraseña** campos como espacio en blanco, el adaptador se conecta a SQL Server mediante autenticación de Windows.|  
  
4.  Haga clic en el **propiedades de URI** y a continuación, especificar valores para los parámetros de conexión. Para obtener más información sobre el URI de conexión para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], consulte [crear el URI de conexión de SQL Server](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).  
  
    > [!NOTE]
    >  Si los parámetros de conexión contienen caracteres reservados, debe especificarlos tal-está en la **propiedades de URI** pestaña, es decir, sin usar cualquier carácter de escape. Sin embargo, si especifica el URI directamente en el **configurar un URI** campo y los parámetros de conexión contienen caracteres reservados, debe especificar los parámetros de conexión con caracteres de escape adecuados.  
  
    > [!NOTE]
    >  Si no especifica ningún valor en la pestaña de propiedades de URI, [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] coloca el URI como `mssql://.//`. En tal caso, el adaptador se conecta a la base de datos predeterminada y a la instancia de base de datos predeterminada en el PC local.  
  
5.  Haga clic en el **propiedades de enlace** ficha y, a continuación, especifique valores para las propiedades de enlace, si existe, requeridos por las operaciones de destino.  
  
6.  Haga clic en **Aceptar**.  
  
7.  Haga clic en **Conectar**. Una vez establecida la conexión, se muestra el estado de conexión como **conectado**.  
  
     La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] inmediatamente después de establecer la conexión. La interfaz gráfica de usuario es el misma para el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
     ![Conectarse a SQL Server](../../adapters-and-accelerators/adapter-sql/media/661adb8a-5050-44d5-8db8-fdf0fe530b40.gif "661adb8a-5050-44d5-8db8-fdf0fe530b40")  
  
     La [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] muestra los distintos nodos que contiene varias operaciones que se pueden realizar en SQL Server. Por ejemplo, el **procedimientos** nodo contiene todos los procedimientos disponibles para la base de datos conectado a. De forma similar, el **tablas** nodo contiene todas las tablas de la base de datos conectados a y las operaciones que pueden realizarse en una tabla. Para obtener más información acerca de estos nodos, consulte [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md).  
  
## <a name="see-also"></a>Vea también  
 [Conectarse a SQL Server en Visual Studio usando el complemento Consume Adapter Service](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)