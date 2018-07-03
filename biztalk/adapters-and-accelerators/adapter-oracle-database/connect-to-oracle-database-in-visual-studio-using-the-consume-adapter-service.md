---
title: Conectarse a la base de datos de Oracle en Visual Studio mediante el servicio de adaptador | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connecting, to the Oracle database
- connection, to the Oracle database
ms.assetid: db2789d0-2d61-472b-ad0c-4ef0707e9c64
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19e83b518e188528b357e52f6397045baeb3ed76
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010484"
---
# <a name="connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service"></a>Conectarse a la base de datos de Oracle en Visual Studio mediante Consume Adapter Service
El complemento Consume Adapter Service se instala al instalar el SDK de adaptador LOB de WCF. El complemento Consume Adapter Service carga todos los enlaces de WCF-Custom instalados en el equipo. Para conectarse a la base de datos de Oracle con el basado en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] en un proyecto de BizTalk, debe usar el **oracleDBBinding**.  

 Este tema proporciona instrucciones sobre cómo usar el complemento Consume Adapter Service.  

## <a name="connecting-to-an-oracle-database-using-the-consume-adapter-service-add-in"></a>Conectarse a Oracle con la base de datos los consumen el adaptador de complemento de servicio  
 Realice los pasos siguientes para conectarse a una base de datos de Oracle mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  

1. Para conectarse mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] en una solución de BizTalk:  

   1. Haga clic en el proyecto en el Explorador de soluciones, seleccione **agregar**y, a continuación, haga clic en **agregar elementos generados**.  

   2. En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:  


      |    Use    |             Para             |
      |----------------|------------------------------------|
      | **Categorías** | Haga clic en **Consume Adapter Service**. |
      | **Templates** (Plantillas [C++])  | Haga clic en **Consume Adapter Service**. |


   3. Haga clic en **Agregar**. Se abrirá [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  

2. Desde el **selecciona un enlace** lista desplegable, seleccione **oracleDBBinding** y haga clic en **configurar**.  

3. En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** ficha y desde el **tipo de credencial de cliente** cuadro de lista desplegable, seleccione **denombredeusuario** y especifique el nombre de usuario y contraseña para conectarse a la base de datos de Oracle.  

   1. Para conectar con las credenciales de la base de datos de Oracle, escriba las credenciales de base de datos en el **nombre de usuario** y **contraseña** cuadros de texto. Asegúrese de que se adhiera a las consideraciones siguientes al especificar el nombre de usuario y contraseña para conectarse a una base de datos de Oracle:  

      - **Nombre de usuario**. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] conserva el caso del valor que especifique para el nombre de usuario cuando se abre una conexión en la base de datos de Oracle. Los nombres de usuario en la base de datos de Oracle distinguen mayúsculas de minúsculas. Debe asegurarse de que proporciona los nombres de usuario de Oracle para el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] en el caso esperado por la base de datos de Oracle. Normalmente, esto significa que el nombre de usuario de la credencial de SCOTT/TIGER debe ser letras mayúsculas: "SCOTT".  

      - **Contraseña**. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] conserva el caso del valor que escriba la contraseña cuando se abre una conexión en la base de datos de Oracle. Para la versión 10g y versiones anteriores, las contraseñas en el sistema Oracle no distinguen mayúsculas de minúsculas.  

   2. Para conectarse mediante la autenticación de Windows, escriba **/** en el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.  

4. Haga clic en el **propiedades de URI** pestaña y especificar valores para los parámetros de conexión. Para obtener más información sobre el URI de conexión para el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [crear el URI de conexión de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).  

5. Haga clic en el **propiedades de enlace** pestaña y, a continuación, especifique valores para las propiedades de enlace, si alguno, requeridos por las operaciones que desea dirigirse. Por ejemplo, si desea tener como destino la operación POLLINGSTMT, debe establecer el **PollingStatement** enlaza la propiedad. Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).  

6. Haga clic en **Aceptar**.  

7. Haga clic en **Conectar**. Una vez establecida la conexión, se muestra el estado de conexión como **conectado**.  

    La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] inmediatamente después de establecer la conexión.  

    ![Consumo de servicio de adaptador de cuadro de diálogo conectado](../../adapters-and-accelerators/adapter-oracle-database/media/b5bdb08c-4326-408b-8c2a-aedae64925c8.gif "b5bdb08c-4326-408b-8c2a-aedae64925c8")  

## <a name="see-also"></a>Vea también  
 [Conectarse a la base de datos de Oracle en Visual Studio mediante Add Adapter Service Reference](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-db-in-visual-studio-using-the-add-adapter-service.md)   
 [Conectarse a la base de datos de Oracle mediante la autenticación de Windows](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)