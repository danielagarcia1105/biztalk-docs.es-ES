---
title: 'Tutorial: Usar el adaptador de BizTalk para TIBCO Enterprise Message Service para recibir datos | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc5a63ec-1897-4c9b-b37f-cdcec151b1c9
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d4f4ac08b979dfc959c6e2ea0aab68b8c07db67
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977525"
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-enterprise-message-service-to-receive-data"></a>Tutorial: Uso del adaptador de BizTalk para TIBCO Enterprise Message Service para recuperar datos
Puede usar el adaptador de BizTalk para TIBCO Enterprise Message Service (EMS) para recibir datos de un sistema TIBCO. En este tutorial se describe un ejemplo de SDK que ilustra este proceso.  

## <a name="prerequisites"></a>Requisitos previos  

- Para el adaptador de BizTalk para TIBCO Enterprise Message Service, es necesario agregar la API de C# de TIBCO EMS, TIBCO.EMS.dll, a la caché global de ensamblados (GAC). Para obtener más información acerca de cómo instalar el ensamblado, vea [TIBCO Enterprise Message Service requisitos y limitaciones](../core/tibco-enterprise-message-service-requirements-and-limitations.md).  

- Instale [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] en en servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el que se ejecuta el adaptador para crear e implementar el ejemplo.  

## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo toma un archivo XML de una carpeta, envía el archivo a una orquestación y luego usa el adaptador de BizTalk para TIBCO Enterprise Message Service para recuperar datos de un sistema TIBCO. El resultado se escribe en un archivo XML.  

## <a name="how-this-sample-is-designed-and-why"></a>Cómo se ha diseñado este ejemplo y por qué  
 Este ejemplo, diseñado en Visual Studio, muestra la funcionalidad básica, el adaptador de BizTalk para TIBCO Enterprise Message Service con una orquestación de BizTalk.  

> [!NOTE]
>  Este ejemplo supone que sabe cómo enviar un mensaje desde TIBCO para que la aplicación lo procese.  

## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 La ubicación predeterminada para el ejemplo es  

 C:\Archivos de programa\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Enterprise Message Service(TM)\Sdk\OneWayReceive  

 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  

|**Nombre de archivo de proyecto en tiempo de ejecución**|**Descripción del archivo de proyecto en tiempo de ejecución**|  
|----------------------------------|------------------------------------------|  
|OneWayReceive.btproj,<br /><br /> OneWayReceive.sln|Archivos de proyectos y soluciones para la aplicación.|  
|Schema.xsd,|Archivo de esquema de la aplicación.|  
|Orchestration.odx|La orquestación usada por la aplicación.|  
|TIBCOEMSOneWaySend.snk|Archivo de clave de nombre seguro.|  

## <a name="how-to-use-this-sample"></a>Uso del ejemplo  

#### <a name="create-a-new-instance-of-the-biztalk-adapter-for-tibco-ems"></a>Crear una nueva instancia del adaptador de BizTalk para TIBCO EMS  

1. Inicie la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Haga clic en **iniciar**, **programas**, **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], **administración de BizTalk Server**.  

2. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, haga clic en  **Adaptadores**.  

3. Haga clic en **adaptadores** y apuntar a **New**, **adaptador** para mostrar el **propiedades del adaptador** cuadro de diálogo.  

4. Escriba un valor para el **nombre** campo, por ejemplo **TIBCO EMS**.  

5. Seleccione **TIBCO Enterprise Message System** en la lista de adaptadores disponibles en el **adaptador** lista desplegable y haga clic en **Aceptar**.  

#### <a name="create-a-biztalk-receive-port"></a>Crear un puerto de recepción de BizTalk  

1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **puertos de recepción**.  

2. Haga clic en la carpeta puertos de recepción y, a continuación, haga clic en **New**, **puerto de recepción unidireccional** para mostrar el cuadro de diálogo Propiedades de puerto de recepción.  

3. Escriba un valor para el **nombre** campo, por ejemplo **TIBCOEMSOneWayRP**y haga clic en **Aceptar**.  

#### <a name="create-a-biztalk-receive-location"></a>Crear una ubicación de recepción de BizTalk  

1. Con el botón secundario del nuevo puerto de recepción y, a continuación, haga clic en **New**, **ubicación de recepción** para mostrar el **propiedades de ubicación de recepción** cuadro de diálogo.  

2. Escriba un valor para el **nombre** campo, por ejemplo **TIBCOEMSOneWayRL**.  

3. Seleccione el adaptador TIBCO EMS en la lista de adaptadores disponibles en el **tipo** lista desplegable y haga clic en el **configurar** botón para mostrar el adaptador **propiedades de transporte** cuadro de diálogo.  

   > [!NOTE]
   >  Este valor es el nombre que se especificó cuando se creó el adaptador TIBCO en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  

4. Escriba valores para el **definición de la conexión de servidor**:  


   | **Propiedad** |                                **Value**                                |
   |--------------|-------------------------------------------------------------------------|
   | Destino  |               Nombre de cola o tema de destino de servidor.               |
   | Número de puerto  | Puerto en el que el servidor TIBCO está escuchando. Valor predeterminado es 7222. |
   | Nombre del servidor  |                    Nombre del servidor TIBCO EMS.                    |


5. Escriba valores para el **las credenciales de usuario**:  

   |**Propiedad**|**Value**|  
   |------------------|---------------|  
   |Contraseña|Contraseña para el servidor TIBCO EMS.|  
   |Nombre de usuario|Nombre de usuario para el servidor TIBCO EMS.|  

    Para obtener más información acerca de las propiedades, vea [crear controladores TIBCO Enterprise Message Service recibir](../core/creating-tibco-enterprise-message-service-receive-handlers.md).  

6. Haga clic en **Aceptar**.  

7. Seleccione **XMLReceive** en la lista de canalizaciones disponibles en el **canalización de recepción** lista desplegable y haga clic en **Aceptar**.  

8. Haga clic en la ubicación de recepción y haga clic en **habilitar**.  

#### <a name="create-a-one-way-file-send-port"></a>Crear un puerto de envío de archivo unidireccional  

1. Cree una carpeta de destino que va a usar el puerto de envío; por ejemplo C:\FilesOut.  

2. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **puertos de envío**.  

3. Haga clic en **puertos de envío** y apuntar a **New**, **puerto de envío unidireccional estático** para mostrar el **propiedades de puerto de envío** cuadro de diálogo.  

4. Escriba un valor para el **nombre** campo, por ejemplo **TIBCOEMSOneWayFileSP**.  

5. Seleccione **archivo** en la lista de adaptadores disponibles en el **tipo** lista desplegable y haga clic en el **configurar** botón para mostrar el adaptador **transporte Propiedades** cuadro de diálogo.  

6. Para el **carpeta de destino** propiedad, escriba la ubicación de la carpeta que creó anteriormente y haga clic en **Aceptar**.  

7. Seleccione el **XMLTransmit** canalización en la lista de canalizaciones disponibles en el **canalización de envío** lista desplegable y haga clic en **Aceptar**.  

8. Haga clic en el puerto de envío y haga clic en **iniciar** para dar de alta e iniciar el puerto de envío.  

#### <a name="build-and-deploy-the-project"></a>Generar e implementar el proyecto  

1. Haga clic en el proyecto OneWayReceive en el Explorador de soluciones y haga clic en **propiedades** para iniciar el Diseñador de proyectos para el proyecto.  

2. Haga clic en el **implementación** ficha.  

3. Escriba los valores adecuados para el **Server** propiedad y el **base de datos de configuración** propiedad bajo **grupo de BizTalk** categoría.  

4. Haga clic en el proyecto OneWayReceive en el Explorador de soluciones y haga clic en **implementar** para compilar el proyecto e implementar el ensamblado en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] base de datos de configuración.  

#### <a name="bind-and-enlist-the-orchestration"></a>Enlazar y dar de alta la orquestación  

1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **orquestaciones**.  

2. Haga clic en el **actualizar** situado en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] barra de herramientas de consola de administración o presione la **F5** en el teclado para actualizar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] vista de la consola de administración.  

3. Haga doble clic en la orquestación para mostrar el **propiedades de orquestación** cuadro de diálogo.  

4. Haga clic en **enlaces** en el panel izquierdo del cuadro de diálogo para mostrar las opciones de enlaces para la orquestación.  

5. Especifique los valores adecuados para las opciones de enlace, por ejemplo:  


   |         **Parámetro**          |        **Value**         |
   |--------------------------------|--------------------------|
   |              Host              | BizTalkServerApplication |
   |          FileSendPort          |   TIBCOEMSOneWayFileSP   |
   | TibcoEMSOneWayReceiveOperation |     TIBCOEMSOneWayRP     |


6. Haga clic en **Aceptar**.  

#### <a name="start-the-orchestration"></a>Iniciar la orquestación  

- En el [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] consola de administración, haga clic en la orquestación y haga clic en **iniciar** para dar de alta e iniciar la orquestación.  

#### <a name="verify-that-the-application-receives-a-message"></a>Comprobar que la aplicación recibe un mensaje  

- Abra la carpeta a la que el puerto de envío de archivos debe enviar elementos y compruebe que se generó un documento de salida. Este archivo debe contener los resultados de la consulta que el adaptador de BizTalk para TIBCO Enterprise Message Service ha procesado.  

  Si la instancia de documento se procesa correctamente, se produce la siguiente secuencia de eventos:  

1.  El adaptador TIBCO EMS recibe un mensaje del sistema TIBCO y lo publica en el cuadro de mensajes como un mensaje de BizTalk.  

2.  La orquestación se suscribe a este mensaje publicado para que el motor de mensajería de BizTalk active una instancia de la orquestación y envíe el mensaje a ésta.  

3.  La instancia de orquestación publica el mensaje en el cuadro de mensajes.  

4.  El puerto de envío de archivos se suscribe a este mensaje, por lo que BizTalk envía el mensaje al adaptador de archivo.  

5.  El adaptador de archivos escribe un mensaje que contiene el conjunto de resultados en la carpeta de salida designada.  

## <a name="see-also"></a>Vea también  
 [Tutorial: Usar el adaptador de BizTalk para TIBCO Enterprise Message Service para enviar datos](../core/tutorial-use-tibco-enterprise-message-service-adapter-in-biztalk-to-send-data.md)   
 [Tutoriales: Uso del adaptador de Microsoft BizTalk para TIBCO Enterprise Message Service](../core/tutorials-use-the-microsoft-biztalk-adapter-for-tibco-message-service.md)   
 [Introducción](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)