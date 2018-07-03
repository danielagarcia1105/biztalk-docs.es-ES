---
title: 'Tutorial: Usar el adaptador de BizTalk para PeopleSoft Enterprise para recuperar datos de PeopleSoft Enterprise | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c173fa4c-911e-4fa3-813f-e8f36b0049a5
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9728e642a1ad9e03e550a652757d33038cbab79d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993429"
---
# <a name="tutorial-using-the-biztalk-adapter-for-peoplesoft-enterprise-to-retrieve-data-from-peoplesoft-enterprise"></a>Tutorial: Uso del adaptador de BizTalk para PeopleSoft Enterprise para recuperar datos de PeopleSoft Enterprise
El adaptador de BizTalk para PeopleSoft Enterprise se puede usar para ejecutar una consulta en un sistema PeopleSoft y devolver los resultados de la misma. En este tutorial se describe un ejemplo de SDK que muestra esta función.  

## <a name="prerequisites"></a>Requisitos previos  

- La plataforma Java 2 debe estar instalada en el servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el que se ejecuta el adaptador de BizTalk para PeopleSoft Enterprise.  

- El archivo JAR de PeopleSoft Java objeto adaptador, **psjoa.jar** se deben copiar en una carpeta que sea accesible para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que se ejecuta el adaptador de BizTalk para PeopleSoft Enterprise.  

- Para crear e implementar el ejemplo, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] debe instalarse en el servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el que se esté ejecutando el adaptador de BizTalk para PeopleSoft Enterprise.  

## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo toma un archivo XML de una carpeta, envía el archivo a una orquestación y, luego, usa el adaptador de BizTalk para PeopleSoft Enterprise para ejecutar una consulta en un sistema PeopleSoft. El resultado de la consulta se escribe en un archivo XML.  

## <a name="how-this-sample-is-designed-and-why"></a>Cómo se ha diseñado este ejemplo y por qué  
 Este ejemplo se ha diseñado en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y se ha creado para mostrar las funciones básicas relacionadas con el uso del adaptador de BizTalk para PeopleSoft Enterprise con una orquestación de BizTalk.  

## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 El ejemplo se encuentra en la siguiente carpeta:  

 \Archivos de programa\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise(r)\Sdk\PeopleSoftTwoWaySend  

 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  


|                               **Nombre de archivo de proyecto en tiempo de ejecución**                                |                                                                                                                                                                           **Descripción del archivo de proyecto en tiempo de ejecución**                                                                                                                                                                            |
|-------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                       TwoWaySend.btproj,<br /><br /> TwoWaySend.sln                       |                                                                                                                                                                      Archivos de proyectos y soluciones para la aplicación.                                                                                                                                                                      |
| LOCATIONService.xsd,<br /><br /> LOCATIONService_1.xsd,<br /><br /> LOCATIONService_2.xsd | Archivos de esquema para la aplicación. **Nota:** los archivos de esquema de adaptador en el proyecto se crearon originalmente con el **Asistente para agregar metadatos de adaptador**. Para obtener más información sobre el Asistente para agregar metadatos de adaptador, vea el tema "Cómo agregar metadatos del adaptador a un proyecto de BizTalk" en la documentación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. |
|                                 PeopleSoftTwoWaySend.odx                                  |                                                                                                                                                                        La orquestación usada por la aplicación.                                                                                                                                                                         |
|                                 PeopleSoftTwoWaySend.snk                                  |                                                                                                                                                                                Archivo de clave de nombre seguro.                                                                                                                                                                                |

## <a name="how-to-use-this-sample"></a>Uso del ejemplo  

#### <a name="create-a-new-instance-of-the-peoplesoft-enterprise-adapter"></a>Crear una nueva instancia del adaptador de PeopleSoft Enterprise  

1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración. Haga clic en **iniciar**, **programas**, **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], **administración de BizTalk Server**.  

2. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, haga clic en  **Adaptadores**.  

3. Haga clic en **adaptadores** y apuntar a **New**, **adaptador** para mostrar el **propiedades del adaptador** cuadro de diálogo.  

4. Escriba un valor para el **nombre** campo, por ejemplo **PeopleSoft**.  

5. Seleccione **PeopleSoft Enterprise (r)** en la lista de adaptadores disponibles en el **adaptador** lista desplegable y haga clic en **Aceptar**.  

#### <a name="create-a-solicit-response-biztalk-send-port"></a>Crear un puerto de envío de petición-respuesta de BizTalk  

1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **puertos de envío**.  

2. Haga clic en **puertos de envío** y apuntar a **New**, **puerto de envío de petición-respuesta estático** para mostrar el **propiedades de puerto de envío** cuadro de diálogo.  

3. Escriba un valor para el **nombre** campo, por ejemplo **PeopleSoftTwoWaySP**.  

4. Seleccione el adaptador de PeopleSoft en la lista de adaptadores disponibles en el **tipo** lista desplegable y haga clic en el **configurar** botón para mostrar el adaptador **propiedades de transporte**cuadro de diálogo.  

   > [!NOTE]
   >  Este valor es el nombre especificado cuando se creó el adaptador de PeopleSoft Enterprise en la consola de administración.  

5. Escriba los siguientes valores para el **propiedades de adaptador necesarias**:  


   |       **Propiedad**       |                                                                                                                                        **Value**                                                                                                                                         |
   |--------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | Ruta de acceso de servidor de aplicaciones  | Equipo y ubicación de puerto de PeopleSoft Server, por ejemplo, //PSServer:8888. **Nota:** si no especifica un número de puerto, se usa el puerto predeterminado 9000 por lo que en el ejemplo anterior puede escribir el valor de //PSServer si PeopleSoft Server usa el valor de puerto predeterminado 9000. |
   |        JAVA_HOME         |                                                                                          Ruta de acceso para el directorio principal asociado a los archivos SDK de la plataforma Java 2, por ejemplo, C:\j2sdk1.4.2_08                                                                                          |
   |         Contraseña         |                                                                                                                 Contraseña usada al conectar con el sistema PeopleSoft.                                                                                                                  |
   | Archivos JAR de PeopleSoft 8.x |                                                                                          Ubicación del archivo JAR de PeopleSoft Java objeto adaptador **psjoa.jar**, por ejemplo, C:\JARS\psjoa.jar.                                                                                          |
   |        Nombre de usuario         |                                                                                                                    Nombre de usuario para conectar con el sistema PeopleSoft.                                                                                                                     |


6. Haga clic en **Aceptar**.  

7. Seleccione el **XMLTransmit** canalización en la lista de canalizaciones disponibles en el **canalización de envío** lista desplegable.  

8. Seleccione el **XMLReceive** canalización en la lista de canalizaciones disponibles en el **canalización de recepción** lista desplegable y haga clic en **Aceptar**.  

9. Haga clic en el puerto de envío y haga clic en **iniciar** para dar de alta e iniciar el puerto de envío.  

#### <a name="create-a-one-way-biztalk-send-port"></a>Crear un puerto de envío unidireccional de BizTalk  

1. Cree la carpeta de destino que va a usar el puerto de envío, por ejemplo, C:\Files\Out.  

2. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **puertos de envío**.  

3. Haga clic en **puertos de envío** y apuntar a **New**, **puerto de envío unidireccional estático** para mostrar el **propiedades de puerto de envío** cuadro de diálogo.  

4. Escriba un valor para el **nombre** campo, por ejemplo **PeopleSoftTwoWayFileSP**.  

5. Seleccione **archivo** en la lista de adaptadores disponibles en el **tipo** lista desplegable y haga clic en el **configurar** botón para mostrar el adaptador **transporte Propiedades** cuadro de diálogo.  

6. Escriba la ubicación de la carpeta que creó anteriormente para la **carpeta de destino** propiedad y haga clic en **Aceptar**.  

7. Seleccione el **XMLTransmit** canalización en la lista de canalizaciones disponibles en el **canalización de envío** lista desplegable y haga clic en **Aceptar**.  

8. Haga clic en el puerto de envío y haga clic en **iniciar** para dar de alta e iniciar el puerto de envío.  

#### <a name="create-a-file-receive-port"></a>Crear un puerto de recepción de archivos  

1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **puertos de recepción**.  

2. Haga clic en la carpeta puertos de recepción y, a continuación, haga clic en **New**, **puerto de recepción unidireccional** para mostrar el cuadro de diálogo Propiedades de puerto de recepción.  

3. Escriba un valor para el **nombre** campo, por ejemplo **PeopleSoftTwoWayFileRP**y haga clic en **Aceptar**.  

#### <a name="create-a-file-receive-location"></a>Crear una ubicación de recepción de archivos  

1.  Cree la carpeta que la ubicación de recepción de archivos supervisará, por ejemplo, C:\Files\In.  

2.  Con el botón secundario del nuevo puerto de recepción y, a continuación, haga clic en **New**, **ubicación de recepción** para mostrar el **propiedades de ubicación de recepción** cuadro de diálogo.  

3.  Escriba un valor para el **nombre** campo, por ejemplo **PeopleSoftTwoWayFileRL**.  

4.  Seleccione **archivo** en la lista de adaptadores disponibles en el **tipo** lista desplegable y haga clic en el **configurar** botón para mostrar el adaptador **transporte Propiedades** cuadro de diálogo.  

5.  Escriba la ubicación de la carpeta que creó anteriormente para la **carpetas de recepción** propiedad y haga clic en **Aceptar**.  

6.  Seleccione **XMLReceive** en la lista de canalizaciones disponibles en el **canalización de recepción** lista desplegable y haga clic en **Aceptar**.  

7.  Haga clic en la ubicación de recepción y haga clic en **habilitar**.  

#### <a name="modify-the-adapter-schema-target-namespace-property"></a>Modificar la propiedad del espacio de nombres de destino del esquema del adaptador  

1. Inicie [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y abra TwoWaySend.sln. Haga clic en **archivo**, **abierto**, **proyecto/solución** para mostrar el **Abrir proyecto** cuadro de diálogo.  

2. Busque el archivo TwoWaySend.sln, haga clic en este archivo para seleccionarlo y haga clic en **abrir** para abrir la solución que contiene el proyecto de ejemplo.  

3. Haga clic en el **vista** menú y seleccione **el Explorador de soluciones** para mostrar el Explorador de soluciones.  

4. Haga doble clic en el archivo LOCATIONService_1.xsd en el Explorador de soluciones para abrirlo.  

5. Haga clic en el **esquema** nodo de LOCATIONService_1.xsd y seleccione el **propiedades** opción de menú para mostrar las propiedades para el esquema.  

6. Editar el **Target Namespace** propiedad que se va a usar los valores adecuados para el nombre del adaptador, por ejemplo el **Target Namespace** propiedad debe indicar lo siguiente:  

   ```  
   http://schemas.microsoft.com/[PeopleSoft://CI/LOCATION]  
   ```  

    Donde *PeopleSoft* es el nombre del adaptador de PeopleSoft, tal como se ve en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.  

   > [!IMPORTANT]
   >  Si el valor configurado para **Target Namespace** no coincide con el espacio de nombres especificado en la instancia de documento de entrada, a continuación, se producirá un error de enrutamiento cuando la instancia de documento de entrada se procesa mediante [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  

#### <a name="generate-a-document-instance-from-the-adapter-schema"></a>Generar una instancia de documento desde el esquema de adaptador  

1.  Haga doble clic en **LOCATIONService_1.xsd** en el Explorador de soluciones para abrir el archivo en el Editor de esquemas.  

2.  Haga clic en el **\<esquema\>** nodo Editor de esquemas y haga clic en **propiedades** para mostrar las propiedades del nodo.  

3.  Seleccione **obtener** en la lista de nodos disponibles en el **referencia raíz** cuadro de lista desplegable. Esto debe hacerse para que cuando se genera una instancia de documento de ejemplo se generará desde el **obtener** nodo del esquema.  

4.  Haga clic en **LOCATIONService_1.xsd** en el Explorador de soluciones y haga clic en **propiedades** para mostrar las propiedades en la ventana Propiedades.  

5.  En la ventana Propiedades, haga clic para seleccionar el **nombre de archivo de instancia de salida** opción.  

6.  Haga clic en el botón de puntos suspensivos (...) para mostrar el **Seleccionar archivo de salida** cuadro de diálogo.  

7.  Especifique una carpeta y un nombre para la instancia de archivo de salida, por ejemplo **C:\instance.xml** y haga clic en **guardar**.  

    > [!NOTE]
    >  No especifique aquí la ubicación de la carpeta que se especificó para la ubicación de recepción de archivos.  

8.  Haga clic en LOCATIONService_1.xsd en el Explorador de soluciones y haga clic en **generar instancia** para generar una instancia de documento en la ubicación especificada.  

9. Haga clic en el **\<esquema\>** nodo Editor de esquemas y haga clic en **propiedades** para mostrar las propiedades del nodo.  

10. Seleccione (**predeterminado)** en la lista de nodos disponibles en el **referencia raíz** cuadro de lista desplegable.  

#### <a name="modify-the-generated-document-instance"></a>Modificar la instancia de documento generada  

1.  Abra la instancia de documento generada en un editor de texto como el Bloc de notas y edite el contenido de la instancia de documento para asegurarse de que los datos de estos campos devolverán un registro existente:  

    ```  
    <ns0:Get xmlns:ns0="http://schemas.microsoft.com/[PeopleSoft://CI/LOCATION]">  
    <ns0:SETID>SHARE</ns0:SETID>  
    <ns0:LOCATION>WFKLOC</ns0:LOCATION>  
    <ns0:getHistory>true</ns0:getHistory>  
    </ns0:Get>  
    ```  

    > [!NOTE]
    >  En el ejemplo anterior, *PeopleSoft* es un marcador de posición para el nombre real del adaptador según se ve en la consola de administración de BizTalk. *Recurso compartido* y *WFKLOC* son marcadores de posición para los valores usados para identificar un registro concreto en el sistema PeopleSoft.  

2.  Guarde la instancia de documento modificada.  

#### <a name="build-and-deploy-the-project"></a>Generar e implementar el proyecto  

1. Haga clic en el proyecto TwoWaySend en el Explorador de soluciones y haga clic en **propiedades** para mostrar el Diseñador de proyectos para el proyecto.  

2. Haga clic en el **implementación** ficha del Diseñador de proyectos.  

3. Escriba los valores adecuados para el **Server** propiedad y el **base de datos de configuración** propiedad bajo **grupo de BizTalk**.  

4. Haga clic en el proyecto TwoWaySend en el Explorador de soluciones y haga clic en **implementar** para compilar el proyecto e implementar el ensamblado en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] base de datos de configuración.  

#### <a name="bind-and-enlist-the-orchestration"></a>Enlazar y dar de alta la orquestación  

1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **orquestaciones**.  

2. Haga clic en el **actualizar** situado en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] barra de herramientas de consola de administración o presione la **F5** en el teclado para actualizar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] vista de la consola de administración.  

3. Haga doble clic en la orquestación para mostrar el **propiedades de orquestación** cuadro de diálogo.  

4. Haga clic en **enlaces** en el panel izquierdo del cuadro de diálogo para mostrar las opciones de enlaces para la orquestación.  

5. Especifique los valores adecuados para las opciones de enlace, por ejemplo:  


   |      **Parámetro**      |        **Value**         |
   |-------------------------|--------------------------|
   |          Host           | BizTalkServerApplication |
   |     FileReceivePort     |  PeopleSoftTwoWayFileRP  |
   | PeopleSoftTwoWaySend678 |    PeopleSoftTwoWaySP    |
   |      ResponsePort       |  PeopleSoftTwoWayFileSP  |


6. Haga clic en Aceptar.  

#### <a name="start-the-orchestration"></a>Iniciar la orquestación  

- En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en la orquestación y haga clic en **iniciar** para dar de alta e iniciar la orquestación.  

#### <a name="drop-a-document-instance-into-the-folder-monitored-by-the-file-receive-location"></a>Soltar una instancia de documento en la carpeta supervisada por la ubicación del archivo de recepción  

-   Copie la instancia de documento que creó anteriormente en la carpeta que la ubicación de recepción de archivos está configurada para supervisar.  

#### <a name="verify-that-the-document-instance-was-processed-by-the-biztalk-adapter-for-peoplesoft-enterprise"></a>Comprobar que el adaptador de BizTalk para PeopleSoft Enterprise procesó la instancia de documento  

- Abra la carpeta a la que el puerto de envío de archivos debe enviar elementos y compruebe que se generó un documento de salida. Este archivo debe contener los resultados de la consulta que ha procesado el adaptador de BizTalk para PeopleSoft Enterprise.  

  Si la instancia de documento se procesa correctamente, se produce la siguiente secuencia de eventos:  

1.  El adaptador de archivo recupera el archivo de la carpeta y lo publica en el cuadro de mensaje como un mensaje de BizTalk.  

2.  La orquestación se suscribe a este mensaje publicado para que el motor de mensajería de BizTalk active una instancia de la orquestación y envíe el mensaje a ésta.  

3.  La instancia de orquestación publica el mensaje en el cuadro de mensajes.  

4.  El puerto de envío de petición-respuesta se suscribe a este mensaje publicado, por lo que el motor de mensajería de BizTalk envía el mensaje al puerto de envío de PeopleSoft.  

5.  El puerto de envío entrega el mensaje al adaptador de BizTalk para PeopleSoft Enterprise.  

6.  El adaptador de BizTalk para PeopleSoft Enterprise ejecuta una instrucción Get en el sistema PeopleSoft usando los parámetros definidos en el archivo de entrada.  

7.  El adaptador de BizTalk para PeopleSoft Enterprise devuelve los resultados de la instrucción Get como mensaje de respuesta para el puerto de petición-respuesta de la orquestación.  

8.  La orquestación publica el conjunto de resultados en el cuadro de mensajes.  

9. El puerto de envío de archivos se suscribe a este mensaje, por lo que BizTalk envía el mensaje al adaptador de archivo.  

10. El adaptador de archivos escribe un mensaje que contiene el conjunto de resultados en la carpeta de salida designada.  

## <a name="see-also"></a>Vea también  
 [Tutoriales: Uso del adaptador de BizTalk para PeopleSoft Enterprise](../core/tutorials-using-biztalk-adapter-for-peoplesoft-enterprise.md)