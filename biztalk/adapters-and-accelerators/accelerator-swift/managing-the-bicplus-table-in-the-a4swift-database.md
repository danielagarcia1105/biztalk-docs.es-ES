---
title: "Administración de la tabla Bicplus en la base de datos de A4SWIFT | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Bank Identifier Code (BIC), Bicplus table
- A4SWIFT database, Bicplus table
- Bicplus table
ms.assetid: a255cdea-5ed4-4481-97f1-8425877a76d6
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a58396a9dd6627f2913da8e3845a99b17cf7698
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="managing-the-bicplus-table-in-the-a4swift-database"></a>Administración de la tabla Bicplus en la base de datos de A4SWIFT
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]utiliza una tabla de entradas BIC para realizar la validación de BIC. Esta tabla puede estar en la tabla de acceso Bicplus en el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] base de datos o una tabla en una base de datos personalizado.  
  
 Para administrar esta tabla, debe rellenar con valores BIC de SWIFT. Si utiliza una base de datos personalizado, también debe exportar vistas de SQL en el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] base de datos en la base de datos personalizado.  
  
## <a name="importing-bic-data-from-the-swift-bicplus-database"></a>Importación de datos BIC desde la base de datos de SWIFT Bicplus  
 Debe rellenar la tabla de entradas BIC (el valor predeterminado o la tabla personalizada) con valores BIC de SWIFT. Los datos de SWIFT BIC están disponibles en un [!INCLUDE[btsExcel](../../includes/btsexcel-md.md)] hoja de cálculo o en una base de datos de Oracle que se actualiza mensualmente. Para obtener más información acerca de los datos de SWIFT BIC, vaya a [http://go.microsoft.com/fwlink/?LinkId=27885](http://go.microsoft.com/fwlink/?LinkId=27885).  
  
 Si utiliza una base de datos personalizado, debe exportar datos BIC desde la base de datos de SWIFT Bicplus en la base de datos personalizado. Debe  
  
 Puede importar datos desde el código BIC [!INCLUDE[btsExcel](../../includes/btsexcel-md.md)] hoja de cálculo proporcionada SWIFT en la tabla de Bicplus la [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] la base de datos, ya que son compatibles. Si importa los datos de la hoja de cálculo SWIFT en no[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] la base de datos, asegúrese de que los campos y las columnas de la base de datos, especialmente la columna BIC, son compatibles con la hoja de cálculo SWIFT.  
  
 La operación de importación no elimina ningún código BIC no publicado cuando actualiza la tabla de destino con los códigos que se publican en la tabla SWIFT.  
  
 Los cambios realizados en la tabla Bicplus de la [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] base de datos se registran en el [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] archivo de registro.  
  
#### <a name="to-import-bic-data-from-the-swift-bicplus-database"></a>Para importar datos BIC de la base de datos de SWIFT Bicplus  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, señale a la versión inistalled de SQL Server y, a continuación, haga clic en **SQL Server Management Studio**.  
  
2.  En conectar al servidor, cuadro de diálogo, haga clic en **conectar**.  
  
3.  En la ventana de Microsoft SQL Server Management Studio, expanda el nodo de servidor y, a continuación, **bases de datos**.  
  
4.  Haga clic en **A4SWIFT**, seleccione **tareas**y, a continuación, haga clic en **importar datos**.  
  
5.  En la importación de SQL Server y la página de bienvenida del Asistente para exportación, haga clic en **siguiente**.  
  
6.  En el **elegir un origen de datos** página, si importa datos BIC desde el Bicplus SWIFT [!INCLUDE[btsExcel](../../includes/btsexcel-md.md)] hoja de cálculo, seleccione **Microsoft Excel** en el **origen de datos** cuadro de texto. Vaya a la ubicación de la hoja de cálculo y seleccione el nombre de archivo de la hoja de cálculo en el **ruta de acceso de archivo de Excel** cuadro de texto. Haga clic en **Siguiente**.  
  
     Si importa datos BIC desde la base de datos de Oracle, seleccione **Microsoft ODBC Driver para Oracle** en el **origen de datos** cuadro de texto. Especifique el servidor con la base de datos de Oracle, el nombre de usuario y contraseña necesaria para conectarse a ese servidor y, a continuación, haga clic en **siguiente**.  
  
7.  En el **elegir un destino** , comprueba que **proveedor Microsoft OLE DB para SQL Server** se escribe en el **destino** cuadro de texto y que **uso Autenticación de Windows** está seleccionada. Si va a llenar la tabla Bicplus en la [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] la base de datos, compruebe que **A4SWIFT** se escribe en el **base de datos** cuadro de texto. Si usa una base de datos personalizado, escriba el nombre de esa base de datos en el **base de datos** cuadro de texto. Haga clic en **Siguiente**.  
  
8.  En el **seleccione copia de la tabla o consulta** , comprueba que **copiar los datos de una o más tablas o vistas** está seleccionada. Si tiene que utilizar una consulta para especificar los datos, seleccione **escribir una consulta para especificar los datos que se va a transferir**. Haga clic en **Siguiente**.  
  
9. En el **seleccionar tablas de origen y vistas** página, haga clic en **Bicplus** en el **origen** columna, seleccione **Bicplus** en el  **Destino** columna y, a continuación, haga clic en **siguiente**.  
  
10. En el **guardar y ejecutar paquete** página, escriba la información de programación adecuada y, a continuación, haga clic en **siguiente**.  
  
11. En el **Complete el asistente** página, revise el resumen y, a continuación, haga clic en **finalizar**.  
  
## <a name="importing-sql-views-from-the-a4swift-database-into-a-custom-database"></a>Importar vistas SQL de la base de datos de A4SWIFT en una base de datos personalizado  
 El [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] programa de instalación instala dos vistas SQL en el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] base de datos. Una vista es de ocho caracteres BICs y el otro es para BICs de 11 caracteres.  
  
 Si utiliza una base de datos personalizada en lugar de la [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] base de datos, debe importar estas vistas SQL en la base de datos personalizado. La forma de hacerlo es mediante la ejecución de la secuencia de comandos CreateBICViews.sql en el analizador de consultas. Este script está en \< *unidad*\>: \Program Acelerador de BizTalk para SWIFT/secuencias de comandos.  
  
#### <a name="to-import-sql-views-from-the-a4swift-database-into-a-custom-database"></a>Para importar vistas SQL de la base de datos de A4SWIFT en una base de datos personalizado  
  
1.  En el Explorador de Windows, desplácese a \< *unidad*\>: \Program Acelerador de BizTalk para SWIFT\Scripts. Haga doble clic en **CreateBICViews.sql**.  
  
2.  En conectar al servidor, cuadro de diálogo, haga clic en **conectar**.  
  
3.  En la ventana de Microsoft SQL Server Management Studio, seleccione **A4SWIFT** en el cuadro de texto de la base de datos.  
  
4.  En el panel de consulta, si está almacenando BICs en una tabla que se denomina distinto de "Bicplus", busque **dbo. Bicplus** en la vista **dbo. Bic11**y cambiarlo al nombre de tabla correspondiente. Haga lo mismo para la vista **dbo. Bic8**.  
  
5.  Si va a almacenar BICs en una columna que se denomina distinto de "BIC", buscar **BIC** en el **seleccione**, **donde**, y **ORDER BY** cláusulas, y cámbielo al nombre de columna adecuado.  
  
6.  Haga clic en **Ejecutar**.  
  
## <a name="see-also"></a>Vea también  
 [Habilitación de la validación de códigos de identificación bancaria](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)