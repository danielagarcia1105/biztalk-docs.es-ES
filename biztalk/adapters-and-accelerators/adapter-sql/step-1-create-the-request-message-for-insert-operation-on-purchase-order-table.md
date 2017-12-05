---
title: "Paso 1: Crear el mensaje de solicitud para la operación de inserción en la tabla Purchase_Order | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fde018d8-9d9a-42ea-8ee9-e3632450b9d7
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 71021bb0a9bbb71f17f0899e625ac184f9087429
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-1-create-the-request-message-for-insert-operation-on-purchaseorder-table"></a>Paso 1: Crear el mensaje de solicitud para la operación de inserción en la tabla Purchase_Order
![Paso 1 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")  
  
 **Tiempo en completarse:** 10 minutos  
  
 **Objetivo:** en este paso, agregará un proyecto de biblioteca de clases de C# a la solución. Esta biblioteca crea un mensaje de solicitud en memoria para la operación de inserción en el **Purchase_Order** tabla. En pasos posteriores, la orquestación envía este mensaje a SQL Server para insertar registros en la tabla.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe haber completado los pasos descritos en [lección 3: ejecutar un procedimiento almacenado que seleccione a nuevos empleados agregar](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md).  
  
### <a name="to-create-a-request-message-for-insert-operation"></a>Para crear un mensaje de solicitud para la operación de inserción  
  
1.  Agregar un proyecto de biblioteca de clases de Visual C# a la solución. Para el nombre del proyecto, escriba `UpdatePOMessageCreator`.  
  
2.  Cambiar el nombre de **Class1.cs** a **UpdatePOMessageCreator.cs**.  
  
3.  Copie el código siguiente en el archivo. cs:  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
    using System.Xml;  
    using System.IO;  
  
    namespace UpdatePOMessageCreator  
    {  
        public class UpdatePOMessageCreator  
        {  
            private static XmlDocument Message;  
            private static string XmlFileLocation;  
            private static string ResponseDoc;  
  
            public static XmlDocument XMLMessageCreator()  
            {  
                XmlFileLocation = "C:\\TestLocation\\CreatePOMessage";  
                try  
                {  
                    ResponseDoc = (Directory.GetFiles(XmlFileLocation, "*.xml", SearchOption.TopDirectoryOnly))[0];  
                }  
                catch (Exception ex)  
                {  
                    Console.WriteLine("Trying to get XML from: " + XmlFileLocation);  
                    Console.WriteLine("EXCEPTION: " + ex.ToString());  
                    throw ex;  
                }  
  
                //Create Message From XML  
                Message = new XmlDocument();  
  
                Message.PreserveWhitespace = true;  
  
                Message.Load(ResponseDoc);  
  
                return Message;  
            }  
        }  
    }  
  
    ```  
  
     Este fragmento de código, espera un mensaje de solicitud para la operación de inserción en el **Purchase_Order** tabla esté presente en C:\TestLocation\CreatePOMessage. El código usa el mensaje de solicitud para crear un mensaje de solicitud similar en tiempo de ejecución.  
  
4.  Agregue un archivo de clave de nombre seguro al proyecto. Para obtener instrucciones sobre cómo crear un archivo de clave de nombre seguro, vea [los requisitos previos para crear aplicaciones de SQL mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md).  
  
    1.  En el Explorador de soluciones, haga clic en el **UpdatePOMessageCreator** del proyecto y haga clic en **propiedades**.  
  
    2.  En el **propiedad** ventana, haga clic en **firma**.  
  
    3.  En el **firma** ficha, seleccione la **firmar el ensamblado** casilla de verificación.  
  
    4.  Desde el **elegir un archivo de clave de nombre seguro** lista, haga clic en  **\<examinar\>**.  
  
    5.  Navegue hasta la carpeta donde se creó el archivo de clave de nombre seguro y, a continuación, haga clic en **abiertos**.  
  
    6.  Haga clic en **guardar** en el **estándar** barra de menús. Cerrar la **propiedad** ventana.  
  
5.  Generar el proyecto. Haga clic en el proyecto y haga clic en **generar**.  
  
6.  Agregue una referencia de este proyecto al proyecto de BizTalk en la solución.  
  
    1.  En el Explorador de soluciones, expanda el proyecto de BizTalk, haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.  
  
    2.  En el **Agregar referencia** cuadro de diálogo, haga clic en el **proyectos** ficha.  
  
    3.  En la lista de nombres de proyecto, seleccione **UpdatePOMessageCreator**, haga clic en **agregar**y, a continuación, haga clic en **Aceptar**.  
  
7.  Compilar el proyecto, crea el archivo DLL del ensamblado en la carpeta \bin\Debug del proyecto. Debe agregar este archivo DLL a la caché de ensamblados Global (GAC).  
  
    1.  Inicie un símbolo del sistema de Visual Studio.  
  
    2.  Desde el símbolo del sistema, navegue hasta la carpeta \bin\Debug\ de la **UpdatePOMessageCreator** proyecto.  
  
    3.  Ejecute el siguiente comando en el símbolo del sistema:  
  
        ```  
        gacutil /i UpdatePOMessageCreator.dll  
        ```  
  
## <a name="what-did-i-just-do"></a>Síntesis  
 En este paso, ha agregado un proyecto de biblioteca de clases de UpdatePOMessageCreator que crea el mensaje de solicitud en tiempo de ejecución. Agregar la referencia a este proyecto en el proyecto de BizTalk y también agrega el archivo DLL del ensamblado a la GAC.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Asignar el mensaje de respuesta para el procedimiento almacenado de UPDATE_EMPLOYEE al mensaje de solicitud para la operación de inserción en **Purchaser_Order** tabla.  
  
## <a name="see-also"></a>Vea también  
 [Paso 2: Asignar el mensaje de respuesta UPDATE_EMPLOYEE insertar el mensaje de solicitud de operación](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md)   
 [Lección 4: Realizar una operación de inserción en la tabla de pedidos de compra](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)