---
title: 'Paso 1: Crear el mensaje de solicitud de UPDATE_EMPLOYEE procedimiento almacenado | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4dd975d9-4b38-46e0-a926-4b325b0d7b5e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e30225b79b14ffc237798ddde6f3fe40fb4aea9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965994"
---
# <a name="step-1-create-the-request-message-for-updateemployee-stored-procedure"></a>Paso 1: Crear el mensaje de solicitud de UPDATE_EMPLOYEE procedimiento almacenado
![Paso 1 de 2](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")  
  
 **Tiempo en completarse:** 10 minutos  
  
 **Objetivo:** en este paso, agregará un proyecto de biblioteca de clases de C# a la solución. Esta biblioteca crea un mensaje de solicitud en memoria para el **UPDATE_EMPLOYEE** procedimiento almacenado. En pasos posteriores, la orquestación envía este mensaje a SQL Server para ejecutar el procedimiento almacenado.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe haber completado los pasos descritos en [lección 2: recibir notificaciones de filtro y](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md).  
  
### <a name="to-create-a-request-message-for-updateemployee-stored-procedure"></a>Para crear un mensaje de solicitud para UPDATE_EMPLOYEE de procedimiento almacenado  
  
1.  Agregar un proyecto de biblioteca de clases de Visual C# a la solución. Para el nombre del proyecto, escriba `UpdateEmployeeMessageCreator`.  
  
2.  Cambiar el nombre de **Class1.cs** a **UpdateEmployeeMessageCreator.cs**.  
  
3.  Copie el código siguiente en el archivo. cs:  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
    using System.Xml;  
    using System.IO;  
  
    namespace UpdateEmployeeMessageCreator  
    {  
        public class UpdateEmployeeMessageCreator  
        {  
            private static XmlDocument Message;  
            private static string XmlFileLocation;  
            private static string ResponseDoc;  
  
            public static XmlDocument XMLMessageCreator()  
            {  
                XmlFileLocation = "C:\\TestLocation\\CreateEmployeeMessage";  
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
  
     Este fragmento de código espera un mensaje de solicitud para la **UPDATE_EMPLOYEE** procedimiento almacenado para estar presente en C:\TestLocation\CreateEmployeeMessage. El código usa el mensaje de solicitud para crear un mensaje de solicitud similar en tiempo de ejecución.  
  
4.  Agregue un archivo de clave de nombre seguro al proyecto. Vea [los requisitos previos para crear aplicaciones de SQL mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md).  
  
    1.  En el Explorador de soluciones, haga clic en el **UpdateEmployeeMessageCreator** del proyecto y, a continuación, haga clic en **propiedades**.  
  
    2.  En el **propiedad** ventana, haga clic en **firma**.  
  
    3.  En el **firma** ficha, seleccione la **firmar el ensamblado** casilla de verificación.  
  
    4.  Desde el **elegir un archivo de clave de nombre seguro** lista, haga clic en  **\<examinar\>**.  
  
    5.  Navegue hasta la carpeta donde se creó el archivo de clave de nombre seguro y, a continuación, haga clic en **abiertos**.  
  
    6.  Haga clic en **guardar** en la barra de menús estándar. Cerrar la **propiedad** ventana.  
  
5.  Generar el proyecto. Haga clic en el proyecto y, a continuación, haga clic en **generar**.  
  
6.  Agregue una referencia de este proyecto al proyecto de BizTalk en la solución.  
  
    1.  En el Explorador de soluciones, expanda el proyecto de BizTalk, haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.  
  
    2.  En el **Agregar referencia** cuadro de diálogo, haga clic en el **proyectos** ficha.  
  
    3.  En la lista de nombres de proyecto, seleccione **UpdateEmployeeMessageCreator**, haga clic en **agregar**y, a continuación, haga clic en **Aceptar**.  
  
7.  Compilar el proyecto, crea el archivo DLL del ensamblado en la carpeta \bin\Debug del proyecto. Debe agregar este archivo DLL a la caché de ensamblados Global (GAC).  
  
    1.  Inicie un símbolo del sistema de Visual Studio.  
  
    2.  Desde el símbolo del sistema, navegue hasta la carpeta \bin\Debug\ de la **UpdateEmployeeMessageCreator** proyecto.  
  
    3.  Ejecute el siguiente comando en el símbolo del sistema:  
  
        ```  
        gacutil /i UpdateEmployeeMessageCreator.dll  
        ```  
  
## <a name="what-did-i-just-do"></a>Síntesis  
 En este paso, ha agregado un proyecto de biblioteca de clases de UpdateEmployeeMessageCreator que crea el mensaje de solicitud en tiempo de ejecución. Agregar la referencia a este proyecto en el proyecto de BizTalk y también agrega el archivo DLL del ensamblado a la GAC.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Enviar el mensaje de solicitud a SQL Server y recibir la respuesta, como se describe en [paso 2: enviar el mensaje de solicitud a SQL Server y recibir respuesta](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md).  
  
## <a name="see-also"></a>Vea también  
 [Lección 3: Ejecutar un procedimiento almacenado para seleccionar nuevos empleados agregados](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)