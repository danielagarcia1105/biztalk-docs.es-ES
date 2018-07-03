---
title: Ejecutar procedimientos almacenados con un solo parámetro XML en SQL Server mediante BizTalk Server | Microsoft Docs
description: Pasar un único parámetro en un procedimiento almacenado mediante el puerto de WCF-Custom y el adaptador de SQL en BizTalk
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: deb9333a-5e28-4e8d-8e0b-07b5a97a111b
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a71ee5be554393db10e65adb49694e7104bb011b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976927"
---
# <a name="execute-stored-procedures-with-a-single-xml-parameter-in-sql-server-using-biztalk-server"></a>Ejecutar procedimientos almacenados con un solo parámetro XML en SQL Server mediante BizTalk Server
Ejecutar un procedimiento almacenado que toma un único parámetro es similar a la ejecución de cualquier otro procedimiento almacenado como se describe en [ejecutar procedimientos almacenados en SQL Server mediante BizTalk Server](execute-stored-procedures-in-sql-server-using-biztalk-server.md). Sin embargo, para el enfoque descrito en el vínculo anterior, deberá generar metadatos para el procedimiento almacenado en tiempo de diseño y creación de una orquestación para invocar el procedimiento en tiempo de ejecución.  
  
 Considere un escenario donde desea pasar un valor único a un procedimiento almacenado sin tener que realizar ningún procesamiento en ese valor. En tales casos, no desea la sobrecarga de generación de metadatos, crear una orquestación, implementación de la orquestación y ejecutar la operación. En su lugar, puede configurar un WCF-Custom o el puerto de envío WCF-SQL para invocar directamente el procedimiento almacenado. En este tema se muestra cómo realizar estas tareas mediante el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
> [!NOTE]
>  Este tema proporciona instrucciones sobre cómo configurar un WCF-Custom puerto de envío para ejecutar un procedimiento almacenado que toma un parámetro único. Puede realizar los mismos pasos mediante la configuración de un puerto de WCF-SQL. Para obtener instrucciones sobre cómo configurar el puerto WCF-SQL, consulte [configurar un puerto mediante el adaptador de WCF-SQL](configure-a-port-using-the-wcf-sql-adapter.md).  
  
## <a name="invoke-stored-procedures-without-orchestration"></a>Invocar procedimientos almacenados sin orquestación  
 Para demostrar cómo ejecutar procedimientos almacenados con parámetros de inicio único sin una orquestación, este tema usa el procedimiento almacenado de ADD_LAST_EMP_XML_INFO. Este procedimiento toma un valor XML como parámetro y lo inserta en la **dirección** columna de la **empleado** tabla. Debe tener el valor XML que pasará al procedimiento almacenado. Sin embargo, para ejecutar el procedimiento almacenado mediante el adaptador, debe enviar un mensaje de solicitud que cumplen el esquema del procedimiento y que contiene el XML de valor para el **dirección** campo a SQL Server. Por lo tanto, debe crear ese mensaje de solicitud por:  
  
- Mediante el **plantilla** opción en la configuración de puerto de envío con que puede crear un mensaje de solicitud mediante una plantilla de mensaje.  
  
- Colocar el código XML de valor para el **dirección** campo en el mensaje.  
  
  Todos estos pasos se describen en detalle en este tema. Debe realizar el siguiente conjunto de tareas:  
  
1. Cree un archivo donde se colocará el archivo XML que se insertará en el puerto de recepción la **dirección** campo XML de la **empleado** tabla. Supongamos que se llama a este puerto **MessageIn** puerto.  
  
2. Cree un puerto de envío unidireccional personalizado de WCF que recoge el archivo XML desde el archivo de puerto de recepción, construye el mensaje mediante la plantilla de mensaje y lo envía a SQL Server para ejecutar el procedimiento almacenado.  
  
   Esta parte del tema proporciona instrucciones sobre cómo configurar un WCF-Custom puerto de envío con la plantilla de mensaje.  
  
> [!NOTE]
>  Aunque la información de este tema muestra cómo ejecutar un procedimiento almacenado con un solo parámetro XML, puede realizar las tareas para realizar cualquier operación que toma un único parámetro de cualquier tipo de datos. La única diferencia estará en el modo de que crear una plantilla de mensaje para una operación específica. Puede crear una plantilla de mensaje tomando el mensaje de solicitud que se utilizaría para ejecutar la operación mediante una orquestación y reemplazando el valor del parámetro con BizTalk, el cuerpo del mensaje.  
  
##  <a name="BKMK_OneWay"></a> Configurar un puerto de envío WCF-Custom  
 Antes de crear el WCF-Custom, puerto de envío, asegúrese de que se creó el archivo de puerto de recepción, **MessageIn**.  
  
1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2. En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
3. Expanda la aplicación en la que desea implementar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
4. Haga clic en **puertos de envío**, apunte a **New**y, a continuación, elija **puerto de envío unidireccional estático**.  
  
5. En el **propiedades de puerto de envío** cuadro de diálogo el **General** , escriba un nombre para el puerto de envío.  
  
6. Configurar el puerto para recibir todos los mensajes que se puede quitados el archivo de puerto de recepción, **MessageIn**.  
  
   1.  En el **propiedades de puerto de envío** cuadro de diálogo, en el panel izquierdo, haga clic en **filtros**.  
  
   2.  En el panel derecho, bajo el **propiedad** columna, haga clic en la cuadrícula y, a continuación, seleccione **BTS. ReceivePortName** propiedad.  
  
   3.  Para el **operador** columna, seleccione "**==**".  
  
   4.  Para el **valor** columna, especifique el nombre del archivo de puerto de recepción, `MessageIn`.  
  
7. En el **propiedades de puerto de envío** cuadro de diálogo el **General** ficha, desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **Configurar**.  
  
8. En el **propiedades de transporte WCF-Custom** diálogo cuadro, realice lo siguiente:  
  
   1. Haga clic en el **General** ficha y en el **dirección (URI)** campo, especifique el URI de conexión para SQL Server. Para obtener más información sobre el URI de conexión, consulte [crear el URI de conexión de SQL Server](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).  
  
   2. En el **General** ficha la **acción** texto, escriba la acción para la operación. Consulte [mensajes y esquemas de mensaje](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md) para obtener una lista de acciones para cada operación. Por ejemplo, la acción que se invoca el ADD_LAST_EMP_XML_INFO es:  
  
      ```  
      Procedure/dbo/ADD_LAST_EMP_XML_INFO  
      ```  
  
   3. Haga clic en el **enlace** ficha y desde el **BindingType** lista, seleccione **sqlBinding**. Puede especificar las propiedades de enlace diferente expuestas por la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).  
  
   4. Haga clic en el **credenciales** pestaña y, a continuación, realice uno de los siguientes:  
  
      -   Seleccione el **no use Single Sign-On** opción, especifique el nombre de usuario y contraseña para conectarse a SQL Server. Tenga en cuenta que el nombre de usuario y la contraseña distinguen entre mayúsculas y minúsculas.  
  
          > [!NOTE]
          >  Si desea conectarse a SQL Server mediante la autenticación de Windows, especifique un nombre de usuario y una contraseña.  
  
      -   Seleccione el **Use Single Sign-On** opción y, a continuación, especifique un inicio de sesión único empresarial (SSO) de la aplicación afiliada.  
  
           Para obtener más información acerca de la seguridad con respecto a BizTalk Server, consulte [seguridad con el adaptador de SQL y BizTalk Server](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md).
  
   5. Haga clic en el **mensajes** ficha y en el **cuerpo del mensaje saliente de WCF** sección, elija el **plantilla** opción.  
  
   6. En el **XML** texto, especifique la plantilla que se usará para construir el mensaje WCF. Al hacerlo, crea un mensaje que se ajusta a la operación ADD_LAST_EMP_XML_INFO basada en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
       ![Especificar plantilla para mensaje WCF saliente](../../adapters-and-accelerators/adapter-sql/media/012e9ff0-b78f-4a1d-8a3a-a7b8e3850d55.gif "012e9ff0-b78f-4a1d-8a3a-a7b8e3850d55")  
  
       Para conocer el procedimiento almacenado de ADD_LAST_EMP_XML_INFO, debe especificar la siguiente plantilla:  
  
      ```  
      <ADD_LAST_EMP_XML_INFO xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/dbo">  
      <xml_info>  
      <bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="string"/>  
      </xml_info>  
      </ADD_LAST_EMP_XML_INFO>  
      ```  
  
      > [!IMPORTANT]
      >  La codificación en la plantilla de mensaje, siempre debe ser "string", independientemente del tipo del parámetro para la operación que se invoca mediante el puerto de envío. Por ejemplo, el ADD_LAST_EMP_XML_INFO toma un parámetro de tipo XML, pero la codificación en la plantilla de mensaje es la cadena.  
      > 
      > [!NOTE]
      >  Puede crear esta plantilla de mensaje copiando el mensaje de solicitud para el procedimiento almacenado y reemplazando el valor dentro de las etiquetas < xml_info > por el cuerpo del mensaje de BizTalk. Puede obtener el mensaje de solicitud para el procedimiento almacenado mediante la generación del esquema para el procedimiento mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]y, a continuación, generar una instancia del esquema para obtener la solicitud de XML.  
  
   7. Para volver a la **propiedades de puerto de envío** cuadro de diálogo, haga clic en **Aceptar**.  
  
9. Desde el **controlador de envío** lista, seleccione **BizTalkServerApplication**.  
  
10. Desde el **canalización de envío** lista, seleccione la canalización que corresponde a **PassThruTransmit**.  
  
11. Haga clic en **Aceptar**.  
  
## <a name="start-the-application"></a>Iniciar la aplicación  
 Para iniciar la aplicación de BizTalk, puede iniciar el archivo de ubicación de recepción y el puerto de envío personalizada de WCF individualmente. Debe ahora copia un archivo XML a la carpeta que se asigna al archivo de la ubicación de recepción. La aplicación de BizTalk consume el archivo y el valor XML se inserta en la columna de dirección de la tabla Employee. Puede comprobarlo mediante un cliente de SQL Server y seleccionar los registros de la tabla Employee.  
  
## <a name="using-a-two-way-wcf-custom-send-port"></a>Uso de un puerto de envío WCF-Custom bidireccional  
 Las instrucciones de este tema, en la sección [cómo configurar un puerto de envío WCF-Custom](../../core/how-to-configure-a-wcf-custom-send-port.md), se muestra cómo configurar un puerto de envío unidireccional de WCF-Custom para ejecutar un procedimiento almacenado con un único parámetro sin usar BizTalk orquestación. Sin embargo, en tal caso, para comprobar si el procedimiento almacenado se ejecuta correctamente debe comprobar en la base de datos de SQL Server si se actualiza la columna de dirección en la tabla Employee.  
  
 En su lugar, puede crear un puerto de envío WCF-Custom bidireccional que se obtiene también la respuesta de SQL Server si el procedimiento almacenado se ejecuta correctamente. Debe realizar algunos pasos adicionales si crea un puerto bidireccional de WCF-Custom. Tenga en cuenta que todavía necesitará un archivo de ubicación de recepción, como se mencionó en las instrucciones anteriores.  
  
1. Crear un puerto de envío WCF-Custom bidireccional, por ejemplo, **ExecProcedure**. Los pasos para configurar el puerto de envío son similares a las del puerto de envío unidireccional. La única diferencia es que para el puerto bidireccional también debe especificar una canalización de recepción. Asegúrese de seleccionar **PassThruReceive** para la canalización de recepción.  
  
2. Cree un puerto de envío de archivos. Este puerto quitará el mensaje de respuesta de la base de datos de SQL Server en una carpeta. Mediante el **filtros** ficha del cuadro de diálogo Propiedades de puerto, configure el puerto de envío de archivo para recibir todos los mensajes de respuesta desde el puerto de envío WCF-Custom.  
  
   1.  En el **propiedades de puerto de envío** cuadro de diálogo, en el panel izquierdo, haga clic en **filtros**.  
  
   2.  En el panel derecho, bajo el **propiedad** columna, haga clic en la cuadrícula y, a continuación, seleccione **BTS. SPName** propiedad.  
  
   3.  Para el **operador** columna, seleccione "**==**".  
  
   4.  Para el **valor** columna, especifique el puerto de envío el nombre de la WCF-Custom `ExecProcedure`.  
  
   Iniciar todos los puertos de tres. Copia un archivo XML a la carpeta que se asigna al archivo de la ubicación de recepción. Busque la respuesta en la carpeta asignada al puerto de envío de archivo.  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)