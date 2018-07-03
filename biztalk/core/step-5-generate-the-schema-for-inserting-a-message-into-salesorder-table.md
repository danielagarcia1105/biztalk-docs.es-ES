---
title: 'Paso 5 (local): Generar el esquema para insertar un mensaje en la tabla SalesOrder | Microsoft Docs'
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
ms.openlocfilehash: afdca03f5ad8639705ac40171e4142a12c07d757
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973477"
---
# <a name="step-5-on-premises-generate-the-schema-for-inserting-a-message-inito-salesorder-table"></a>Paso 5 (local): Generar el esquema para insertar un mensaje en la tabla SalesOrder
Según el escenario empresarial, el X12 envía el mensaje de pedido de ventas de Contoso debe insertarse de Northwind **SalesOrder** tabla si la cantidad pedida es superior a 100. Para insertar un mensaje en un **SalesOrder** tabla, debe generar el esquema para el **insertar** operación en la tabla. En este tema, creará un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución y, a continuación, utilice el [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)] para generar el esquema para llevar a cabo una **insertar** operación en el **SalesOrder** tabla.  

### <a name="to-generate-the-schema-for-insert-operation-on-salesorder-table"></a>Para generar el esquema para la operación Insertar en la tabla SalesOrder  

1. Cree un proyecto de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Visual Studio. Desde Visual Studio **archivo** menú, haga clic en **New**y, a continuación, haga clic en **proyecto**. En el **nuevo proyecto** haga clic en el cuadro de diálogo, en la lista de plantillas instaladas, **proyectos de BizTalk**y, a continuación, seleccione **vacía [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proyecto**. Escriba el nombre del proyecto `OrderProcessingDemo` y, a continuación, haga clic en **Aceptar**.  

2. Haga clic en el nombre del proyecto en el Explorador de soluciones, seleccione **agregar**y, a continuación, haga clic en **agregar elementos generados**.  

3. En el **agregar elementos generados** cuadro de diálogo, seleccione **Consume Adapter Service**y, a continuación, haga clic en **agregar**. Se abrirá [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)].  

4. Desde el **selecciona un enlace** lista desplegable, seleccione **sqlBinding**y, a continuación, haga clic en **configurar**.  

5. En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** ficha y desde el **tipo de credencial de cliente** lista desplegable, realice una de las siguientes acciones:  


   |  Haga clic en  |                                                                                                                                                               Para                                                                                                                                                               |
   |--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |   **Ninguno**   |                                                                                                                                          Conéctese a SQL Server mediante la autenticación de Windows.                                                                                                                                           |
   | **Windows**  |                                                                                                                                          Conéctese a SQL Server mediante la autenticación de Windows.                                                                                                                                           |
   | **Nombre de usuario** | Especifique un nombre de usuario y una contraseña para conectarse a SQL Server especificando credenciales para un usuario definido en la base de datos de SQL Server. Tenga en cuenta que el nombre de usuario y la contraseña distinguen entre mayúsculas y minúsculas. **Nota:** si deja el **nombre de usuario** y **contraseña** campos en blanco, el adaptador se conecta a SQL Server mediante la autenticación de Windows. |


6. Haga clic en el **propiedades de URI** pestaña y, a continuación, especifique valores para los parámetros de conexión. Para obtener más información sobre el URI de conexión para el [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], consulte [URI de conexión de SQL Server](http://msdn.microsoft.com/library/dd788089.aspx).  

   > [!NOTE]
   >  Si los parámetros de conexión contienen caracteres reservados, deberá especificarlos como-está en el **propiedades de URI** pestaña, es decir, sin usar cualquier carácter de escape. Sin embargo, si especifica el URI directamente en el **configurar un URI** campo y los parámetros de conexión contienen caracteres reservados, debe especificar los parámetros de conexión con los caracteres de escape adecuados.  
   > 
   > [!NOTE]
   >  Si no especifica ningún valor en la pestaña de propiedades de URI, [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)] coloca el URI como `mssql://.//`. En tal caso, el adaptador se conecta a la base de datos predeterminada y a la instancia de base de datos predeterminada en el PC local.  

7. En el **configurar el adaptador** cuadro de diálogo, haga clic en **Aceptar**. En el **Consume Adapter Service** cuadro de diálogo, haga clic en **Connect**.  

8. Desde el **seleccionar una categoría** , expanda **tablas**y, a continuación, haga clic en el **SalesOrder** tabla.  

9. Desde el **operaciones y categorías disponibles** cuadro, seleccione **insertar**, haga clic en **agregar**y, a continuación, haga clic en **Aceptar**. Se agregarán los nuevos elementos al explorador de soluciones. El archivo de esquema (**TableOperation.dbo.SalesOrder.xsd**) es el esquema generado para realizar una operación de inserción en el **SalesOrder** tabla.  

## <a name="see-also"></a>Vea también  
 [Tutorial 4: Crear una aplicación híbrida con BizTalk Server 2013](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)