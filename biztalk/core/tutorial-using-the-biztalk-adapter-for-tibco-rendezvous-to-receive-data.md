---
title: 'Tutorial: Usar el adaptador de BizTalk para TIBCO Rendezvous para recibir datos | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58e7a739-701d-4085-a840-54f81c55e943
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de436413f10cf4882b5c4e4b21af7bac6a3234c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-receive-data"></a>Tutorial: Usar el adaptador de BizTalk para TIBCO Rendezvous para recibir datos
Puede usar el Adaptador de BizTalk para TIBCO Rendezvous para recibir datos de un sistema TIBCO. En este tutorial se describe un ejemplo de SDK que ilustra este proceso.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Instale [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] en en servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el que se ejecuta el adaptador para crear e implementar el ejemplo.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo usa el Adaptador de BizTalk para TIBCO Rendezvous para recibir datos de un sistema TIBCO. Una orquestación procesa el mensaje y, mediante el adaptador de archivos, escribe los datos como un archivo XML en una carpeta especificada.  
  
## <a name="how-this-sample-is-designed-and-why"></a>Cómo se ha diseñado este ejemplo y por qué  
 Este ejemplo, diseñado en [!INCLUDE[vs2010](../includes/vs2010-md.md)], ilustra funciones básicas mediante el uso del adaptador de BizTalk para TIBCO Enterprise Message Service con una orquestación de BizTalk.  
  
> [!NOTE]
>  Este ejemplo supone que sabe cómo enviar un mensaje desde TIBCO para que la aplicación lo procese.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 La ubicación predeterminada para el ejemplo es  
  
 C:\Archivos de programa\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWayReceive  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|**Nombre de archivo de proyecto en tiempo de ejecución**|**Descripción del archivo del proyecto en tiempo de ejecución**|  
|----------------------------------|------------------------------------------|  
|OneWayReceive.btproj,<br /><br /> OneWayReceive.sln|Archivos de proyectos y soluciones para la aplicación.|  
|PureMessage.xsd,|Archivo de esquema de la aplicación.|  
|TIBCORvOWR.odx|La orquestación usada por la aplicación.|  
|TIBCORv.snk|Archivo de clave de nombre seguro.|  
  
## <a name="how-to-use-this-sample"></a>Uso del ejemplo  
  
#### <a name="create-a-new-instance-of-the-biztalk-adapter-for-tibco-rendezvous"></a>Crear una nueva instancia del Adaptador de BizTalk para TIBCO Rendezvous  
  
1.  Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración. Haga clic en **iniciar**, **todos los programas**, [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].  
  
2.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, haga clic en **adaptadores**.  
  
3.  Haga clic en **adaptadores** y seleccione **New**, **adaptador...** para mostrar la **propiedades del adaptador** cuadro de diálogo.  
  
4.  Escriba un valor para el **nombre** campo, por ejemplo **TIBCO Rendezvous**.  
  
5.  Seleccione **TIBCO Rendezvous(r)** en la lista de adaptadores disponibles en la **adaptador** lista desplegable y haga clic en **Aceptar**.  
  
#### <a name="create-a-biztalk-receive-port"></a>Crear un puerto de recepción de BizTalk  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **puertos de recepción**.  
  
2.  Haga clic en la carpeta puertos de recepción y, a continuación, haga clic en **New**, **puerto de recepción unidireccional...**  para mostrar la **propiedades de puerto de recepción** cuadro de diálogo.  
  
3.  Escriba un valor para el **nombre** campo, por ejemplo **TIBCORvOneWayRP**y haga clic en **Aceptar**.  
  
#### <a name="create-a-biztalk-receive-location"></a>Crear una ubicación de recepción de BizTalk  
  
1.  Menú contextual del nuevo puerto de recepción y, a continuación, haga clic en **New**, **ubicación de recepción...** para mostrar la **propiedades de la ubicación de recepción** cuadro de diálogo.  
  
2.  Escriba un valor para el **nombre** campo, por ejemplo **TIBCORvOneWayRL**.  
  
3.  Seleccione el adaptador de TIBCO Rendezvous en la lista de adaptadores disponibles en la **tipo** lista desplegable y haga clic en el **configurar** botón para mostrar el adaptador **propiedades de transporte** cuadro de diálogo.  
  
    > [!NOTE]
    >  Este valor es el nombre que se especificó cuando se creó el adaptador TIBCO en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
4.  Escriba un valor para el **RendezvousSubjectName** en el **AdapterRequiredProperties**.  
  
5.  Escriba valores para la **propiedades de escucha certificadas**:  
  
    |**Propiedad**|**Valor**|  
    |------------------|---------------|  
    |Nombre de archivo de contabilidad|Nombre del archivo de contabilidad que se va a usar para la entrega de mensajes certificados persistentes.|  
    |Nombre reutilizable|Nombre reutilizable correspondiente que se va a usar para la entrega de mensajes certificados. El nombre debe ser único entre todos los nombres de correspondientes de mensajes certificados en la red.|  
  
6.  Escriba valores para la **credenciales**:  
  
    |**Propiedad**|**Valor**|  
    |------------------|---------------|  
    |Contraseña|La contraseña para el servidor TIBCO Rendezvous.|  
    |Nombre de usuario.|El nombre de usuario para el servidor TIBCO Rendezvous.|  
  
7.  Escriba valores para la **RendezvousTransport**:  
  
    |**Propiedad**|**Valor**|  
    |------------------|---------------|  
    |Demonio|Parámetro del demonio del transporte de Rendezvous.|  
    |Red|Parámetro de red del transporte de Rendezvous.|  
    |ssNoVersion|Parámetro de servicio del transporte de Rendezvous.|  
  
     Para obtener más información acerca de las propiedades, vea [propiedades de transporte de recepción de configuración de TIBCO Rendezvous](../core/setting-tibco-rendezvous-receive-transport-properties.md).  
  
8.  Haga clic en **Aceptar**.  
  
9. Seleccione **XMLReceive** en la lista de canalizaciones disponibles en la **canalización de recepción** lista desplegable y haga clic en **Aceptar**.  
  
10. Haga clic en la ubicación de recepción y haga clic en **habilitar**.  
  
#### <a name="create-a-one-way-file-send-port"></a>Crear un puerto de envío de archivo unidireccional  
  
1.  Cree una carpeta de destino que va a usar el puerto de envío; por ejemplo C:\FilesOut.  
  
2.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **puertos de envío**.  
  
3.  Haga clic en **puertos de envío** y seleccione **New**, **puerto de envío unidireccional estático...** para mostrar la **propiedades de puerto de envío** cuadro de diálogo.  
  
4.  Escriba un valor para el **nombre** campo, por ejemplo **TIBCORvOneWayFileSP**.  
  
5.  Seleccione **archivo** en la lista de adaptadores disponibles en la **tipo** lista desplegable y haga clic en el **configurar** botón para mostrar el adaptador **transporte Propiedades** cuadro de diálogo.  
  
6.  Para el **carpeta de destino** propiedad, escriba la ubicación de la carpeta que creó anteriormente y haga clic en **Aceptar**.  
  
7.  Seleccione el **XMLTransmit** canalización en la lista de canalizaciones disponibles en la **canalización de envío** lista desplegable y haga clic en **Aceptar**.  
  
8.  Haga clic en el puerto de envío y haga clic en **iniciar** para dar de alta e iniciar el puerto de envío.  
  
#### <a name="build-and-deploy-the-project"></a>Generar e implementar el proyecto  
  
1.  Haga clic en el proyecto OneWayReceive en el Explorador de soluciones y haga clic en **propiedades** para iniciar el Diseñador de proyectos para el proyecto.  
  
2.  Haga clic en el **implementación** ficha.  
  
3.  Escriba los valores adecuados para el **Server** propiedad y el **base de datos de configuración** propiedad bajo **grupo de BizTalk** categoría.  
  
4.  Haga clic en el proyecto OneWayReceive en el Explorador de soluciones y haga clic en **implementar** para crear el proyecto e implementar el ensamblado en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] base de datos de configuración.  
  
#### <a name="bind-and-enlist-the-orchestration"></a>Enlazar y dar de alta la orquestación  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **orquestaciones**.  
  
2.  Haga clic en el **actualizar** botón en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] barra de herramientas de consola de administración o presione la **F5** clave de su teclado para actualizar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] vista de la consola de administración.  
  
3.  Haga doble clic en la orquestación para mostrar el **propiedades de orquestación** cuadro de diálogo.  
  
4.  Haga clic en **enlaces** en el panel izquierdo del cuadro de diálogo para mostrar las opciones de enlaces para la orquestación.  
  
5.  Especifique los valores adecuados para las opciones de enlace, por ejemplo:  
  
    |**Parámetro**|**Valor**|  
    |-------------------|---------------|  
    |Host|BizTalkServerApplication|  
    |SendPort|TIBCORvOneWayFileSP|  
    |ReceivePort|TIBCORvOneWayRP|  
  
6.  Haga clic en **Aceptar**.  
  
#### <a name="start-the-orchestration"></a>Iniciar la orquestación  
  
-   En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en la orquestación y haga clic en **iniciar** dar de alta e iniciar la orquestación.  
  
#### <a name="verify-that-the-application-receives-a-message"></a>Comprobar que la aplicación recibe un mensaje  
  
-   Abra la carpeta a la que el puerto de envío de archivos debe enviar elementos y compruebe que se generó un documento de salida.  
  
 Si la instancia de documento se procesa correctamente, se produce la siguiente secuencia de eventos:  
  
1.  El adaptador de TIBCO Rendezvous recibe un mensaje del sistema TIBCO y lo publica en el cuadro de mensajes como un mensaje de BizTalk.  
  
2.  La orquestación se suscribe a este mensaje publicado para que el motor de mensajería de BizTalk active una instancia de la orquestación y envíe el mensaje a ésta.  
  
3.  La instancia de orquestación publica el mensaje en el cuadro de mensajes.  
  
4.  El puerto de envío de archivos se suscribe a este mensaje, por lo que BizTalk envía el mensaje al adaptador de archivo.  
  
5.  El adaptador de archivos escribe un mensaje que contiene el conjunto de resultados en la carpeta de salida designada.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Usar el adaptador de BizTalk para TIBCO Rendezvous para enviar datos](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-send-data.md)   
 [Tutoriales: Usar el adaptador de Microsoft BizTalk para TIBCO Rendezvous](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md)   
 [Introducción](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)