---
title: 'Paso 5 (local): Generar el esquema para insertar un mensaje en la tabla SalesOrder | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab0bc1a7-8bcd-4110-88e6-4eddf0b57068
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: facb5d638ed82e1632e434a2a9c9063a2c3daa68
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279324"
---
# <a name="step-5-on-premises-generate-the-schema-for-inserting-a-message-inito-salesorder-table"></a>Paso 5 (local): Generar el esquema para insertar un mensaje en la tabla SalesOrder
Según el escenario empresarial, el X12 envía el mensaje de pedido de ventas de Contoso debe insertarse en de Northwind **SalesOrder** tabla si la cantidad pedida es superior a 100. Para insertar un mensaje en una **SalesOrder** tabla, debe generar el esquema para el **insertar** operación en la tabla. En este tema, aprenderá a crear un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución y, a continuación, utilice la [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)] para generar el esquema para llevar a cabo una **insertar** operación en el **SalesOrder** tabla.  
  
### <a name="to-generate-the-schema-for-insert-operation-on-salesorder-table"></a>Para generar el esquema para la operación Insertar en la tabla SalesOrder  
  
1.  Cree un proyecto de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Visual Studio. Desde Visual Studio **archivo** menú, haga clic en **New**y, a continuación, haga clic en **proyecto**. En el **nuevo proyecto** cuadro de diálogo, en la lista de plantillas instaladas, haga clic en **proyectos de BizTalk**y, a continuación, seleccione **vacía [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proyecto**. Para el nombre del proyecto, escriba `OrderProcessingDemo` y, a continuación, haga clic en **Aceptar**.  
  
2.  Haga clic en el nombre del proyecto en el Explorador de soluciones, seleccione **agregar**y, a continuación, haga clic en **agregar elementos generados**.  
  
3.  En el **agregar elementos generados** cuadro de diálogo, seleccione **Consume Adapter Service**y, a continuación, haga clic en **agregar**. Se abrirá [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)].  
  
4.  Desde el **selecciona un enlace** lista desplegable, seleccione **sqlBinding**y, a continuación, haga clic en **configurar**.  
  
5.  En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** ficha y desde el **tipo de credencial de cliente** lista desplegable, realice una de las siguientes acciones:  
  
    |Haga clic en|Para|  
    |----------------|----------------|  
    |**Ninguno**|Conéctese a SQL Server mediante la autenticación de Windows.|  
    |**Windows**|Conéctese a SQL Server mediante la autenticación de Windows.|  
    |**Nombre de usuario**|Especifique un nombre de usuario y una contraseña para conectarse a SQL Server especificando credenciales para un usuario definido en la base de datos de SQL Server. Tenga en cuenta que el nombre de usuario y la contraseña distinguen entre mayúsculas y minúsculas. **Nota:** si deja la **nombre de usuario** y **contraseña** campos como espacio en blanco, el adaptador se conecta a SQL Server mediante autenticación de Windows.|  
  
6.  Haga clic en el **propiedades de URI** y a continuación, especificar valores para los parámetros de conexión. Para obtener más información sobre el URI de conexión para el [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], consulte [URI de conexión de SQL Server](http://msdn.microsoft.com/library/dd788089.aspx).  
  
    > [!NOTE]
    >  Si los parámetros de conexión contienen caracteres reservados, debe especificarlos tal-está en la **propiedades de URI** pestaña, es decir, sin usar cualquier carácter de escape. Sin embargo, si especifica el URI directamente en el **configurar un URI** campo y los parámetros de conexión contienen caracteres reservados, debe especificar los parámetros de conexión con caracteres de escape adecuados.  
  
    > [!NOTE]
    >  Si no especifica ningún valor en la pestaña de propiedades de URI, [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)] coloca el URI como `mssql://.//`. En tal caso, el adaptador se conecta a la base de datos predeterminada y a la instancia de base de datos predeterminada en el PC local.  
  
7.  En el **configurar el adaptador** cuadro de diálogo, haga clic en **Aceptar**. En el **Consume Adapter Service** cuadro de diálogo, haga clic en **conectar**.  
  
8.  Desde el **seleccione una categoría de** , expanda **tablas**y, a continuación, haga clic en el **SalesOrder** tabla.  
  
9. Desde el **categorías y operaciones disponibles** cuadro, seleccione **insertar**, haga clic en **agregar**y, a continuación, haga clic en **Aceptar**. Se agregarán los nuevos elementos al explorador de soluciones. El archivo de esquema (**TableOperation.dbo.SalesOrder.xsd**) es el esquema generado para realizar una operación de inserción en el **SalesOrder** tabla.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 4: Crear una aplicación híbrida mediante BizTalk Server 2013](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)