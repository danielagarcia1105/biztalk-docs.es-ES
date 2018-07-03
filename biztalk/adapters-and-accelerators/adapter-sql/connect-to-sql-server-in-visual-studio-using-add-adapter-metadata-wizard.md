---
title: Conectarse a SQL Server en Visual Studio mediante metadatos Asistente para agregar adaptador | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2169722d-beba-4d96-a54b-54986ece9bf8
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6de95e2e6906a840e0e41d013f6c1e1e0a73a8d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981405"
---
# <a name="connect-to-sql-server-in-visual-studio-using-add-adapter-metadata-wizard"></a>Conectarse a SQL Server en Visual Studio mediante metadatos Asistente para agregar adaptador
El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] también se expone como un adaptador de BizTalk y, por lo tanto, puede usar el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar el esquema para las operaciones que desea realizar en SQL Server con el adaptador.  

## <a name="connecting-to-sql-server-using-add-adapter-metadata-wizard"></a>Conexión a SQL Server mediante metadatos Asistente para agregar adaptador  
 Realice los pasos siguientes para conectarse a SQL Server mediante el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].  

#### <a name="to-connect-to-sql-server"></a>Para conectarse a SQL Server  

1. Para conectarse mediante la [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] en una solución de BizTalk:  

   1. Cree un proyecto de BizTalk con [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].  

   2. Haga clic en el nombre del proyecto en el Explorador de soluciones, seleccione **agregar**y, a continuación, haga clic en **agregar elementos generados**.  

   3. En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:  


      |    Use    |           Para            |
      |----------------|---------------------------------|
      | **Categorías** |     Haga clic en **agregar adaptador**.      |
      | **Templates** (Plantillas [C++])  | Haga clic en **agregar metadatos de adaptador**. |


   4. Haga clic en **Agregar**. Se abrirá [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].  

   5. En el Asistente para agregar adaptador, seleccione **WCF-SQL**. Seleccione el equipo en el que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] está instalado y el nombre de la base de datos de BizTalk.  

      > [!IMPORTANT]
      >  Si ya tiene un puerto de WCF-SQL configurado en BizTalk, seleccione el puerto desde el **puerto** lista.  

   6. Haga clic en **Siguiente**.  

2. Desde el **selecciona un enlace** lista desplegable, seleccione **sqlBinding**y, a continuación, haga clic en **configurar**.  

3. En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** ficha y desde el **tipo de credencial de cliente** lista desplegable, realice una de las siguientes acciones:  

   > [!NOTE]
   >  Si se conecta a SQL Server mediante la autenticación de Windows, el usuario de Windows con la que ha iniciado sesión debe agregarse a SQL Server como se describe en [conectar con SQL Server mediante la autenticación de Windows con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).  

   |  Haga clic en  |                                                                                                                                                               Para                                                                                                                                                               |
   |--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |   **Ninguno**   |                                                                                                                                         Conectarse a SQL Server mediante la autenticación de Windows.                                                                                                                                         |
   | **Windows**  |                                                                                                                                         Conectarse a SQL Server mediante la autenticación de Windows.                                                                                                                                         |
   | **Nombre de usuario** | Especifique un nombre de usuario y una contraseña para conectarse a SQL Server especificando credenciales para un usuario definido en la base de datos de SQL Server. Tenga en cuenta que el nombre de usuario y la contraseña distinguen entre mayúsculas y minúsculas. **Nota:** si deja el **nombre de usuario** y **contraseña** campos en blanco, el adaptador se conecta a SQL Server mediante la autenticación de Windows. |


4. Haga clic en el **propiedades de URI** pestaña y, a continuación, especifique valores para los parámetros de conexión. Para obtener más información sobre el URI de conexión para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], consulte [crear el URI de conexión de SQL Server](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).  

   > [!NOTE]
   >  Si los parámetros de conexión contienen caracteres reservados, deberá especificarlos como-está en el **propiedades de URI** pestaña, es decir, sin usar cualquier carácter de escape. Sin embargo, si especifica el URI directamente en el **configurar un URI** campo y los parámetros de conexión contienen caracteres reservados, debe especificar los parámetros de conexión con los caracteres de escape adecuados.  
   > 
   > [!NOTE]
   >  Si no especifica ningún valor en la pestaña de propiedades de URI, [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] coloca el URI como `mssql://.//`. En tal caso, el adaptador se conecta a la base de datos predeterminada y a la instancia de base de datos predeterminada en el PC local.  

5. Haga clic en el **propiedades de enlace** pestaña y, a continuación, especifique valores para las propiedades de enlace, si alguno, requeridos por las operaciones que desea dirigirse. Para obtener más información sobre las propiedades de enlace, vea [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).  

   > [!NOTE]
   >  Si va a generar los metadatos mediante [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] y ha seleccionado un puerto de envío WCF-SQL existente, no es necesario especificar las propiedades de enlace. Se seleccionan las propiedades de enlace de la configuración de puerto de envío. Sin embargo, puede especificar las propiedades de enlace que son necesarias en tiempo de diseño, si existe. En este caso, se utilizará los nuevos valores de propiedades de enlace en tiempo de diseño al generar los metadatos. Sin embargo, en tiempo de ejecución los valores especificados para las propiedades de enlace en la configuración del puerto de envío será aplicable.  

6. Haga clic en **Aceptar**.  

7. Haga clic en **Conectar**. Una vez establecida la conexión, se muestra el estado de conexión como **conectado**.  

    La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] inmediatamente después de establecer la conexión. La interfaz gráfica de usuario es el misma para el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].  

    ![Conectarse a SQL Server](../../adapters-and-accelerators/adapter-sql/media/661adb8a-5050-44d5-8db8-fdf0fe530b40.gif "661adb8a-5050-44d5-8db8-fdf0fe530b40")  

    La [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] muestra los diferentes nodos que contiene las distintas operaciones que se pueden realizar en SQL Server. Por ejemplo, el **procedimientos** nodo contiene todos los procedimientos disponibles para la base de datos que se ha conectado a. De forma similar, el **tablas** nodo contiene todas las tablas que conectado a la base de datos y las operaciones que se pueden realizar en una tabla. Para obtener más información acerca de estos nodos, consulte [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md).  

## <a name="see-also"></a>Vea también  
 [Conectarse a SQL Server en Visual Studio mediante el complemento Consume Adapter Service](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)