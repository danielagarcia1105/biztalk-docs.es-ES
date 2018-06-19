---
title: 'Paso 4: Probar la aplicación | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 488b13fa-7a71-4430-bbf5-dbf47ba55562
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 347c2bcf459d7e9ce7b1fb9efc07579be81d989d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223036"
---
# <a name="step-4-test-the-application"></a>Paso 4: Probar la aplicación
![Paso 4 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")  
  
 **Tiempo en completarse:** 10 minutos  
  
 **Objetivo:** en este paso, probará la aplicación mediante la inserción de un registro en el **empleado** tabla de la **ADAPTER_SAMPLES** base de datos. Si la aplicación funciona correctamente, la orquestación recibe una notificación de cambios en el **empleado** tabla. A continuación, la orquestación extrae el tipo de notificación recibida. Si la notificación es para una operación de inserción, la orquestación ejecuta la **UPDATE_EMPLOYEE** procedimiento almacenado y recibe una respuesta. La orquestación extrae los valores de **Id_Empleado** y **nombre** de la respuesta y los inserta en la **Purchase_Order** tabla.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Antes de comenzar con este paso, debe asegurarse de lo siguiente:  
  
-   Un mensaje de solicitud para invocar la **UPDATE_EMPLOYEE** procedimiento almacenado está disponible en C:\TestLocation\CreateEmployeeMessage. El mensaje de solicitud tiene el siguiente aspecto:  
  
    ```  
    <UPDATE_EMPLOYEE xmlns="http://schemas.microsoft.com/Sql/2008/05/TypedProcedures/dbo" />  
    ```  
  
-   Un mensaje de solicitud para invocar la operación de inserción en el **Purchase_Order** tabla está disponible en C:\TestLocation\CreatePOMessage. El mensaje de solicitud tiene el siguiente aspecto:  
  
    ```  
    <Insert xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Purchase_Order">  
      <Rows>  
        <Purchase_Order xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/Tables/dbo">  
          <Employee_ID>10</Employee_ID><Employee_Name>Employee_Name</Employee_Name>  
        </Purchase_Order>  
      </Rows>  
    </Insert>  
    ```  
  
    > [!NOTE]
    >  Los valores para la **Id_Empleado** y **Nombre_Empleado** campos son marcadores de posición. Los valores reales se insertan por la orquestación en tiempo de ejecución.  
  
-   Debe haber completado [paso 3: configurar e iniciar la aplicación](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md).  
  
### <a name="to-test-the-application"></a>Para probar la aplicación  
  
1.  Insertar un registro en el **empleado** tabla. Puede hacerlo ejecutando la siguiente instrucción de SQL Server Management Studio.  
  
    ```  
    INSERT INTO [ADAPTER_SAMPLES].[dbo].[Employee] ([Name] ,[Designation] ,[Salary])  
    VALUES('John Smith' ,'Manager' ,500000)  
    ```  
  
2.  Compruebe el **empleado** tabla en la base de datos. Observará que el nuevo registro se agrega mediante la **estado** columna es "0".  
  
3.  Mantener actualizando el **empleado** registros de la tabla. Observará que la **estado** columna para el nuevo registro ahora está establecido en "1".  
  
4.  Compruebe el **Purchase_Order** tabla. Observará que un registro con el mismo nombre de empleado y designación, como se indica en la instrucción Insert, se agrega a la tabla.  
  
5.  Si proporciona el alias de correo electrónico en la configuración del puerto SMTP, también recibirá un correo electrónico con el mensaje de respuesta para la operación de inserción.  
  
## <a name="what-did-i-just-do"></a>Síntesis  
 Probar la aplicación SampleApplication insertando un registro en el **empleado** tabla.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Si la prueba ha funcionado, enhorabuena. Ha completado la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] tutorial.  
  
 Si no ha funcionado la prueba, compruebe con detenimiento el trabajo realizado para asegurarse de que ha agregado todos los objetos necesarios y de que ha establecido las propiedades de éstos correctamente.  
  
## <a name="see-also"></a>Vea también  
 [Paso 3: Configurar e iniciar la aplicación](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md)   
 [Lección 5: Implementar la solución](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)