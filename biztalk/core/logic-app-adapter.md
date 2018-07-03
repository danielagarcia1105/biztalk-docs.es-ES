---
title: Adaptador de aplicación lógica de uso de BizTalk Server | Microsoft Docs
description: Instalar y configurar el adaptador de Logic Apps para crear un puerto de recepción, la ubicación de recepción y el puerto de envío de BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72f2a5ac-a1f6-4bdb-8c29-8267ede75b17
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e13756fb6310b73f8e7fb88c336bdf2a7bbc1372
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972829"
---
# <a name="logic-app-adapter"></a>Adaptador de aplicación lógica

## <a name="overview"></a>Información general
BizTalk Server utiliza el adaptador de Logic Apps para recibir mensajes desde una aplicación de lógica de Azure, o enviar mensajes a una aplicación de lógica de Azure. 

En Azure, se creará una aplicación lógica. Esta aplicación lógica usa el conector de BizTalk para conectarse a una ubicación de recepción que se crea en el servidor BizTalk Server. En este tema se da por supuesto que tiene cierta familiaridad con Azure Logic Apps. Si está familiarizado con las aplicaciones lógicas, sugerimos [aprender más sobre ellas](https://azure.microsoft.com/documentation/articles/app-service-logic-what-are-logic-apps/)e incluso [crear su propia aplicación lógica](https://azure.microsoft.com/documentation/articles/app-service-logic-create-a-logic-app/).

En este tema, se enumeran los pasos para recibir un mensaje en BizTalk Server desde una aplicación lógica. Dicho de otro modo, la aplicación lógica envía mensajes a un servidor BizTalk Server. El lado de recepción usa aplicaciones de IIS para controlar la comunicación con el servicio de Azure. Si BizTalk Server es local, también se instale una puerta de enlace de datos en el servidor BizTalk Server y crear una puerta de enlace en Azure. 

Si BizTalk Server está instalado en una máquina virtual (VM) de Azure, puede elegir exponer la máquina virtual como un extremo HTTP (obtendrá una dirección URL), o no se exponen como un extremo HTTP. Si exponerla, no es necesario utilizar la puerta de enlace. Puede escribir la dirección URL en el conector de BizTalk en la aplicación lógica. Si no expone la máquina virtual (ninguna dirección URL), a continuación, deberá usar la puerta de enlace. Estos pasos se enumeran en este tema.

También se muestra cómo enviar mensajes de BizTalk Server a una aplicación de lógica de Azure. Dicho de otro modo, la aplicación lógica recibe los mensajes de BizTalk Server. El lado de envío es bastante sencillo, como verá en este tema.

Use este tema para crear una ubicación de recepción y un puerto de envío mediante el adaptador de Logic Apps. Puede usar el adaptador de LogicApp en un servidor de BizTalk en el entorno local (unido al dominio) o una máquina virtual de Azure que ejecuta BizTalk Server. 

## <a name="requirements"></a>Requisitos

- Una suscripción de Azure para iniciar sesión en el portal de Azure y crear una aplicación lógica.
- Opcional. Para enviar un mensaje de prueba a la aplicación lógica, instale una herramienta de prueba de HTTP, como [Fiddler](http://www.telerik.com/fiddler) o [Postman](https://www.getpostman.com/). Si emplea otro método para enviar un mensaje a una aplicación lógica, no debe usar estas herramientas. 

## <a name="receive-messages-from-a-logic-app"></a>Recibir mensajes desde una aplicación lógica

Hay unos pocos pasos implicados para BizTalk Server recibir mensajes desde una aplicación lógica. En esta sección se enumera estos pasos. Es posible que no puede ser exactamente como se muestra la interfaz de usuario en los cambios de Azure, por lo que algunos de los pasos. 

#### <a name="prerequisites"></a>Requisitos previos

- Si BizTalk Server es local, instale y configure el [puerta de enlace de datos local](https://azure.microsoft.com/documentation/articles/app-service-logic-gateway-install/) para Logic Apps. A continuación, en Azure, [crear el recurso de puerta de enlace de datos](https://azure.microsoft.com/documentation/articles/app-service-logic-gateway-connection/) para conectarse al servidor BizTalk Server.
- Si BizTalk Server está instalado en una máquina virtual de Azure y la máquina virtual no se expone como un punto de conexión HTTP, a continuación, instale y configure el [puerta de enlace de datos local](https://azure.microsoft.com/documentation/articles/app-service-logic-gateway-install/) para Logic Apps. A continuación, en Azure, [crear el recurso de puerta de enlace de datos](https://azure.microsoft.com/documentation/articles/app-service-logic-gateway-connection/) para conectarse al servidor BizTalk Server.
- Si BizTalk Server está instalado en una máquina virtual de Azure y la máquina virtual se expone como un punto de conexión HTTP, la puerta de enlace no es necesario o utilizan. 

### <a name="step-1-install-the-logic-app-adapter"></a>Paso 1: Instalar al adaptador de aplicación lógica

El adaptador de aplicación lógica es una descarga independiente y no se incluye con la instalación de BizTalk Server. 

> [!IMPORTANT] 
> Para descargar el LogicAppAdapter.iso:
> 
> 1. Vaya a [adaptador de Microsoft BizTalk Server para las aplicaciones lógicas](https://www.microsoft.com/download/details.aspx?id=54287)y guardar. 
> 2. Abra el LogicAppAdapter.iso y ejecute el **LogicApp Adapter.msi** archivo para instalar.

1. En el servidor BizTalk Server, descargue e instale al adaptador de aplicación lógica. 

2. Haga doble clic **LogicApp Adapter.msi** para instalar. Acepte el contrato de licencia y **instalar**.
3. **Finalizar** la instalación, un reinicio d la **BizTalkServerApplication** y **BizTalkServerIsolatedHost** las instancias de host.

Una vez instalado, tener lo siguiente:

- El adaptador de LogicApp se agrega a la administración de BizTalk.
- El controlador de envío se crea y usa el host BizTalkServerApplication.
- El controlador de recepción se crea como un servicio WCF y usa el host BizTalkServerIsolatedHost.
- El `C:\Program Files (x86)\Microsoft BizTalk Server 2016\LogicApp Adapter` carpeta se crea e incluye dos servicios: administración y ReceiveService. 

    El **administración** usa el conector de BizTalk en una aplicación lógica para conectarse a BizTalk Server mediante la puerta de enlace de datos. Este servicio de administración permite que BizTalk Server recibir mensajes de una aplicación de lógica de Azure mediante la puerta de enlace de datos. Este servicio solo se usa en el lado de recepción de BizTalk. No se utiliza en el lado de envío.

    El **ReceiveService** utilizado por el conector de BizTalk en una aplicación lógica cuando escriba la ubicación de recepción. El **ReceiveService** es responsable de enviar los mensajes de la aplicación lógica. Este servicio solo se usa en el lado de recepción de BizTalk. No se utiliza en el lado de envío.


### <a name="step-2-create-the-iis-applications"></a>Paso 2: Creación de las aplicaciones de IIS

Las aplicaciones de IIS utilizan los servicios de administración y ReceiveService.

Puede ejecutar las aplicaciones de IIS con un nuevo grupo de aplicaciones, o un grupo de aplicaciones existente. La identidad de AppPool requiere la pertenencia a los mismos grupos que la cuenta que ejecuta los servicios de BizTalk, como los grupos de usuarios de la aplicación de BizTalk y usuarios de hosts aislados de BizTalk.  

> [!TIP] 
> Si crea un nuevo grupo de aplicaciones, a continuación, mantenga la versión de .NET CLR de forma predeterminada y canalización administrada. Recuerde, elija una identidad (configuración avanzada) que tiene pertenencia a los mismos grupos de BizTalk que la cuenta de servicio de BizTalk. 

#### <a name="create-the-management-iis-application"></a>Crear la aplicación de administración IIS
La dirección URL de esta aplicación de IIS se usa el conector de BizTalk (en la aplicación lógica) para usar la puerta de enlace de datos en el servidor BizTalk Server.

1. Abra el Administrador de Internet Information Services (IIS).
2. Haga clic en **sitio Web predeterminado**, y **Agregar aplicación**. En esta nueva aplicación: 

    1. Escriba el **Alias** (nombre) para la aplicación, como **IISLogicApp**. 
    2. **Seleccione** el grupo de aplicaciones.
    3. Establecer el **ruta de acceso física** a `C:\Program Files (x86)\Microsoft BizTalk Server 2016\LogicApp Adapter\Management`. 
    3. **Configuración de pruebas** para confirmar el grupo de aplicaciones identidad pasa la autenticación y autorización se comprueba.

3. Seleccione **Aceptar** para guardar los cambios.
4. Abra un explorador web y vaya a `http://localhost/YourApplicationAlias/schemas?api-version=2016-10-26`, tales como `http://localhost/IISLogicApp/Schemas?api-version=2016-10-26`. Una lista de presentación de los esquemas o deba abrir o guardar `schemas.json`. El resultado real depende de su explorador web. Si se produce ninguno de estos, su identidad AppPool posible que falte la pertenencia a los grupos de BizTalk.

#### <a name="create-the-biztalk-receiveservice-iis-application"></a>Crear la aplicación de BizTalk ReceiveService IIS
La dirección URL de esta aplicación de IIS se usa el conector de BizTalk (en la aplicación lógica) al elegir la ubicación de recepción. 

1. Abra el Administrador de Internet Information Services (IIS).
2. Haga clic en **sitio Web predeterminado**, y **Agregar aplicación**. En esta nueva aplicación: 

    1. Escriba el **Alias** (nombre) para la aplicación, como **ReceiveWCFService**. 
    2. **Seleccione** el mismo grupo de aplicaciones como la aplicación de IIS anterior.
    3. Establecer el **ruta de acceso física** a `C:\Program Files (x86)\Microsoft BizTalk Server 2016\LogicApp Adapter\ReceiveService`. 
    3. **Configuración de pruebas** para confirmar el grupo de aplicaciones identidad pasa la autenticación y autorización se comprueba.

3. Seleccione **Aceptar** para guardar los cambios.


### <a name="step-3-create-a-logic-app"></a>Paso 3: Crear una aplicación lógica

1. En el [portal Azure](https://portal.azure.com), cree una nueva aplicación lógica.
2. Agregar el **se recibe cuando una solicitud HTTP** desencadenador.
3. Agregar el **BizTalk Server - preparar mensaje desde JSON** acción. 
4. **Opcional**: seleccione **conectarse mediante una puerta de enlace de datos locales**y escriba lo siguiente: 

    | Property | Descripción |
   | --- | --- |
    | Dirección URL del servidor de BizTalk | Escriba el nombre de dominio completo (FQDN) de la administración de BizTalk en la dirección URL de la aplicación de IIS. Por ejemplo, escriba `http://BizTalkServerName.corp.contoso.com/IISLogicApp/`. |
    | Tipo de autenticación | Seleccione **Windows**. |
   | Nombre de usuario | Escriba la identidad del grupo de aplicaciones IIS. |
   | Contraseña | Escriba la contraseña del grupo de aplicaciones IIS. |
   | Puerta de enlace | Seleccione la puerta de enlace que creó. |

    > [!TIP] 
    > Recuerde que la puerta de enlace de datos solo es obligatorio si:
    > - Usa un servidor de BizTalk en el entorno local
    > - Está usando una máquina virtual de Azure de BizTalk Server *y* la máquina virtual no se expone como un extremo HTTP (ninguna dirección URL)

5. Seleccione **Crear**. 
6. Configurar la acción. Para **cuerpo**, seleccione la salida del cuerpo HTTP. Para **esquema**, seleccione el esquema que desea usar. 

    > [!NOTE] 
    > Este paso se supone que está familiarizado con los esquemas de BizTalk y sabe qué esquema deseado. Si no está seguro, a continuación, implementar el ejemplo HelloWorld SDK, actualice sus artefactos para usar el adaptador de aplicación lógica y use su esquema y ejemplo de mensaje. 

7. Agregue un nuevo paso y seleccione el **BizTalk Server: Enviar mensaje** acción. Para **ubicación de recepción**, seleccione la dirección URL de la lista desplegable o escriba el nombre de dominio completo (FQDN) de la dirección URL de aplicación de ReceiveService IIS. Por ejemplo, escriba `http://BizTalkServerName.corp.contoso.com/ReceiveWCFService/Service1.svc`.

    > [!TIP] 
    > Al crear la ubicación de recepción, esta dirección URL exacta deberá especificarse también en las propiedades de transporte de la ubicación de recepción como el **dirección pública** (pestaña General).

    Para **cuerpo**, seleccione la salida del cuerpo de la acción anterior de BizTalk Server. 

8. **Guardar** los cambios. 

Cuando se guarda, el desencadenador de solicitud de HTTP crea automáticamente una dirección URL. Copie esta dirección URL; necesitarla en **paso 5: enviar un mensaje**.

### <a name="step-4-create-a-receive-port-and-a-receive-location"></a>Paso 4: Crear un puerto de recepción y una ubicación de recepción

> [!NOTE] 
> En lugar de crear puertos de su recepción y ubicación de recepción, puede implementar el ejemplo HelloWorld SDK. Actualizar los artefactos para usar el adaptador de Logic Apps. 
 
Esta sección enumeran los pasos para crear sus propios artefactos. 

1. En administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda la aplicación que desea Ejecute la ubicación de recepción. Por ejemplo, expanda **BizTalk Application 1**.
2. Botón derecho, seleccione **puertos de recepción**, seleccione **New**y seleccione **puerto de recepción unidireccional**.
3. En las propiedades de puerto de recepción, escriba lo siguiente:  

    | Use | Para |
    | --- | --- |
    | **Nombre** | Escriba un nombre para el puerto de recepción. Por ejemplo, escriba **LAReceivePort**. |
    | **Autenticación** | Opciones: <br/><ul><li>Sin autenticación: predeterminado. Deshabilita la autenticación.</li><li>Eliminar mensajes si hay errores de autenticación: habilita la autenticación, pero a colocación de los mensajes no autenticados.</li><li>Conservar mensajes si hay errores de autenticación: haga clic en esta opción para habilitar la autenticación y mantener los mensajes no autenticados. </li></ul>|
    | **Habilitar enrutamiento para mensajes con errores** | Enruta los mensajes que se produce un error de procesamiento de una aplicación de suscripción (por ejemplo, otro programación de orquestación o puerto de recepción). Desactive esta opción para suspender los mensajes con errores y generar una confirmación negativa (NACK). Esta opción está desactivada de forma predeterminada. Para obtener más información, consulte [cómo habilitar enrutamiento para mensajes de error para un puerto de recepción](../core/how-to-enable-routing-for-failed-messages-for-a-receive-port.md).|

4. Seleccione **ubicaciones de recepción**y seleccione **New**. 
5. Escriba un **nombre** para la ubicación de recepción. Por ejemplo, escriba **LAReceiveLoc**.
6. Para el **tipo**, seleccione **LogicApp** en la lista y seleccione el **botón configurar**. 
7. En el **General** pestaña, configure la dirección de punto de conexión para la aplicación lógica:

    | Use | Para |
    | --- | --- |
    | **Dirección (URI)** | Requerido. Escriba la dirección URL de aplicación de BizTalk ReceiveService IIS (`/YourIISApp2Name/Service1.svc`). Por ejemplo, escriba `/ReceiveWCFService/Service1.svc`. |
    | **Dirección pública** | Requerido. Escriba `http://<your fully qualified machine name>/YourIISApp2Name/Service1.svc`. Por ejemplo, escriba `http://btsProd.northamerica.corp.contoso.com/ReceiveWCFService/Service1.svc`. <br/><br/>Esta dirección URL exacta también aparece en la aplicación lógica en la ubicación de recepción.|

8. **Opcional**. En el **enlace** pestaña, configure las propiedades relacionadas con la codificación del enlace de WCF-WebHttp subyacente y cualquier tiempo de espera. Estas propiedades son útiles cuando se trabaja con mensajes de gran tamaño.

    | Use | Para |
    | --- | --- |
    | Tiempo de espera de abrir | Escriba el intervalo de tiempo que tardará la operación de apertura del canal en completarse. Este valor debe ser mayor o igual que System.TimeSpan.Zero. <br/><br/>Valor predeterminado: 00:01:00<br/>Valor máximo: 23:59:59 |
    | Tiempo de espera de envío |Escriba el intervalo de tiempo que tardará en completarse la operación de envío. Este valor debe ser mayor o igual que System.TimeSpan.Zero. Si usa una respuesta de solicitud de puerto de recepción, este valor especifica un intervalo de tiempo para la interacción en completarse, incluso si el cliente devuelve un mensaje grande. <br/><br/>Valor predeterminado: 00:01:00<br/>Valor máximo: 23:59:59|
    | Tiempo de espera de cierre | Escriba el intervalo de tiempo que tardará la operación de cierre de canal para completarse. Este valor debe ser mayor o igual que System.TimeSpan.Zero. <br/><br/>Valor predeterminado: 00:01:00<br/>Valor máximo: 23:59:59 |
    | Tamaño máximo de mensaje recibido (bytes) | Escriba el tamaño máximo, en bytes, de un mensaje incluyendo los encabezados, que se reciban en la conexión. El tamaño de los mensajes está enlazado por la cantidad de memoria asignada para cada mensaje. Puede usar esta propiedad para limitar la exposición a ataques por denegación de servicio (DoS). <br/><br/>Valor predeterminado: 65536<br/>Valor máximo: 2147483647|
    | Número máximo de llamadas concurrentes | Escriba el número de llamadas simultáneas a una instancia de servicio único. Las llamadas que superan el límite se ponen en cola. Establecer este valor en 0 es equivalente a establecerlo en Int32.MaxValue. <br/><br/>El valor predeterminado es 200.|

9. **Opcional**. En el **seguridad** pestaña, configure las propiedades de seguridad. Para fines de desarrollo, puede elegir Ninguno:

    | Use | Para |
    | --- | --- |
    | Modo de seguridad | Opciones:  <br/><br/><ul><li>None: Los mensajes no están protegidos durante la transferencia.</li><li>Transporte: Se proporciona seguridad mediante el transporte HTTPS. Los mensajes SOAP están protegidos mediante HTTPS. Para usar este modo, debe establecer la seguridad de Secure Sockets Layer (SSL) en Internet Information Services (IIS). </li><li>TransportCredentialOnly: predeterminado. </li></ul> |
    | Tipos de credencial de transporte del cliente | Elija el tipo de credencial al utilizar la autenticación de cliente. Opciones:  <br/><br/><ul><li>None: No se produce autenticación en el nivel de transporte.</li><li>Basic: Usa la autenticación básica para enviar los nombres de usuario y contraseñas en texto sin formato a través de la red. Debe crear las cuentas de dominio o de usuario local correspondientes a las credenciales.</li><li>Implícita: La autenticación implícita usa envíe contraseñas como un valor hash a través de la red. Solo está disponible en los dominios con controladores de dominio con la autenticación de los sistemas operativos Windows Server. Debe crear las cuentas de dominio o de usuario local correspondientes a las credenciales del cliente.</li><li>NTLM: predeterminado. Los clientes envía las credenciales sin enviar una contraseña a esta ubicación de recepción. Debe crear las cuentas de dominio o de usuario local correspondientes a las credenciales del cliente.</li><li>Windows: Autenticación integrada de Windows negocia Kerberos o NTLM; prefiere Kerberos si hay un dominio. Para usar Kerberos, es importante que el cliente identifique el servicio con un nombre principal de servicio (SPN). Debe crear las cuentas de dominio o de usuario local correspondientes a las credenciales del cliente.</li><li>Certificado: Se usa un certificado de cliente. La cadena de certificados de CA para los certificados X.509 de cliente deben instalarse en el almacén de certificados entidades emisoras raíz de confianza de este equipo para que los clientes puedan autenticarse a esta ubicación de recepción.</li><li>InheritedFromHost</li></ul> |
    | Utilizar Inicio de sesión único (SSO) | |


10. **Opcional**. En el **mensajes** , utilice el **encabezados HTTP salientes** propiedad para agregar los encabezados personalizados y usar las propiedades adicionales para ayudar con errores: 

    | Use | Para |
    | --- | --- |
    |Encabezados HTTP salientes | Escriba los encabezados HTTP que se desean que aparezca en el mensaje de respuesta. | 
    | Deshabilitar ubicación en caso de error | Deshabilita la ubicación de recepción si se produce un error en el procesamiento de entrada debido a un error de canalización de recepción o un error de enrutamiento. Valor predeterminado es desactivado.|
    | Suspender mensaje de solicitud en caso de error | Suspende el mensaje de solicitud si se produce un error en el procesamiento de entrada debido a un error de canalización de recepción o un error de enrutamiento. Valor predeterminado es desactivado.|
    | Incluir detalle de excepción en errores | Cuando se produce un error, devuelve un error de SOAP para facilitar la depuración. Valor predeterminado es desactivado.|

[Administrar ubicaciones de recepción](../core/managing-receive-locations.md) se describen las propiedades adicionales. 

### <a name="step-5-send-a-message"></a>Paso 5: Enviar un mensaje

1. Abra Fiddler o Postman (o lo que prefiera).
2. Pegue la dirección URL del desencadenador de solicitud desde la aplicación lógica. Esta dirección URL que copió en el paso 3. 
3. Seleccione **POST** como el verbo HTTP y ha establecido la **Content-type** encabezado para `application/json`. En el cuerpo, pegue el siguiente JSON:  

    ```json
    {“hello”:”world”}
    ```

4. Se trata de una llamada unidireccional a BizTalk, el resultado debe ser un HTTP 202. Si usa el ejemplo HelloWorld SDK, vaya al servidor BizTalk server. Puede haber un archivo en la carpeta de envío. 


## <a name="send-messages-to-a-logic-app"></a>Enviar mensajes a una aplicación lógica

### <a name="step-1-install-the-logic-apps-adapter"></a>Paso 1: Instalar al adaptador de Logic Apps

El adaptador de Logic Apps es una descarga independiente y no se incluye con la instalación de BizTalk Server.

1. Vaya a [adaptador de Microsoft BizTalk Server para las aplicaciones lógicas](https://www.microsoft.com/download/details.aspx?id=54287)y guardar. 
2. Abra el LogicAppAdapter.iso y ejecute el **LogicApp Adapter.msi** archivo para instalar.
3. **Finalizar** la instalación y reinicie el **BizTalkServerApplication** y **BizTalkServerIsolatedHost** las instancias de host.

Una vez instalado, tener lo siguiente:

- El adaptador de LogicApp se agrega a la administración de BizTalk
- El controlador de envío se crea y usa el host BizTalkServerApplication.
- El controlador de recepción se crea como un servicio WCF y usa el host BizTalkServerIsolatedHost.
- El `C:\Program Files (x86)\Microsoft BizTalk Server 2016\LogicApp Adapter` carpeta se crea e incluye dos servicios: administración y ReceiveService. Estos servicios no se usan para enviar mensajes a una aplicación lógica. 


### <a name="step-2-create-a-logic-app"></a>Paso 2: Crear una aplicación lógica

1. En el [portal Azure](https://portal.azure.com), cree una nueva aplicación lógica.
2. Agregar el **se recibe cuando una solicitud HTTP** desencadenador
3. Agregar el **Office 365 Outlook - enviar un correo electrónico** acción. Para el **a** de direcciones, escriba su dirección de Office 365. Para el **asunto**, escriba `Sending from BizTalk`. Para **cuerpo**, elija el *cuerpo* de salida desde el **se recibe cuando una solicitud HTTP** desencadenador. 
4. Es similar a la aplicación lógica: 

    ![LogicAppExample](../core/media/logicappexample.gif)

5. Copie la dirección URL de POST de HTTP que se crea automáticamente cuando se guarda la aplicación lógica; necesita esta dirección URL en el paso siguiente. Es posible que deba cerrar y volver a abrir la aplicación lógica para ver la dirección URL.  


### <a name="step-3-create-a-send-port"></a>Paso 3: Crear un puerto de envío

Para que BizTalk Server enviar mensajes a una aplicación lógica, la aplicación lógica debe tener un **Manual** desencadenar, tales como **Manual: cuando una solicitud HTTP se recibe**. 

1. En administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda la aplicación que desea Ejecute el puerto de envío. Por ejemplo, expanda **BizTalk Application 1**.
2. Botón derecho, seleccione **puertos de envío**, seleccione **New**y seleccione **puerto de envío unidireccional estático**.
3. Escriba un **nombre** del puerto de envío. Por ejemplo, escriba **LASendPort**.
4. Para el **tipo**, seleccione **LogicApp** en la lista y seleccione el **configurar** botón. 
5. En el **General** pestaña, configure el **URI de devolución de llamada** de su desencadenador de aplicación lógica. Hay dos formas de hacerlo: 

    **Opción 1** : pegue la URL de HTTP POST que copió en el paso anterior en el **desencadenador (URI de devolución de llamada)** propiedad. También puede copiar el URI mediante los siguientes pasos:  
  
   1. En el [portal Azure](https://portal.azure.com), abra la aplicación lógica en el Diseñador de Logic Apps (modo de edición). 
   2. Seleccione el **se recibe cuando una solicitud HTTP** tarjeta y copie el **URL**. 
   3. En el puerto de envío, pegue esta dirección URL en el **desencadenador (URI de devolución de llamada)** propiedad.

      > [!TIP] 
      > También puede usar la API de administración para obtener este identificador URI.

      **Opción 2** : si no conoce el identificador URI de devolución de llamada para el desencadenador, seleccione **configurar**e inicie sesión en Azure. A continuación, utilice las listas desplegables para elegir su **suscripción**, **grupo de recursos**, **aplicación lógica**, y **desencadenador**.
 
6. **Opcional**. En el **enlace** pestaña, configure las propiedades relacionadas con la codificación del enlace de WCF-WebHttp subyacente y cualquier tiempo de espera. Estas propiedades son útiles cuando se trabaja con mensajes de gran tamaño.

    | Use | Para |
    | --- | --- |
    | Tiempo de espera de abrir | Escriba el intervalo de tiempo que tardará la operación de apertura del canal en completarse. Este valor debe ser mayor o igual que System.TimeSpan.Zero. <br/><br/>Valor predeterminado: 00:01:00<br/>Valor máximo: 23:59:59 |
    | Tiempo de espera de envío |Escriba el intervalo de tiempo que tardará en completarse la operación de envío. Este valor debe ser mayor o igual que System.TimeSpan.Zero. Si usa una respuesta de solicitud de puerto de recepción, este valor especifica un intervalo de tiempo para la interacción en completarse, incluso si el cliente devuelve un mensaje grande. <br/><br/>Valor predeterminado: 00:01:00<br/>Valor máximo: 23:59:59|
    | Tiempo de espera de cierre | Escriba el intervalo de tiempo que tardará la operación de cierre de canal para completarse. Este valor debe ser mayor o igual que System.TimeSpan.Zero. <br/><br/>Valor predeterminado: 00:01:00<br/>Valor máximo: 23:59:59 |
    | Tamaño máximo de mensaje recibido (bytes) | Escriba el tamaño máximo, en bytes, de un mensaje incluyendo los encabezados, que se reciban en la conexión. El tamaño de los mensajes está enlazado por la cantidad de memoria asignada para cada mensaje. Puede usar esta propiedad para limitar la exposición a ataques por denegación de servicio (DoS). <br/><br/>El adaptador de lógica appa aprovecha la [clase WebHttpBinding](https://msdn.microsoft.com/library/system.servicemodel.webhttpbinding.aspx) en el modo de transferencia almacenado en búfer para comunicarse con un punto de conexión. El modo de transporte almacenado en búfer el [WebHttpBinding.MaxBufferSize](https://msdn.microsoft.com/library/system.servicemodel.webhttpbinding.maxbuffersize.aspx) propiedad siempre es igual al valor de esta propiedad.  <br/><br/>Valor predeterminado: 65536<br/>Valor máximo: 2147483647 |


7. **Opcional**. En el **mensajes** , utilice el **encabezados HTTP salientes** propiedad para agregar los encabezados personalizados en el mensaje saliente. 
8. Seleccione **Aceptar** para guardar la configuración. 

[Administración de puertos de envío y grupos de puertos de envío](../core/managing-send-ports-and-send-port-groups.md) se describen las propiedades de puerto de envío adicionales. 

### <a name="step-4-send-some-messages"></a>Paso 4: Enviar algunos mensajes

Puede crear un puerto de recepción y ubicación de recepción mediante el adaptador de archivo. Asegúrese de que la aplicación lógica está habilitada.

1. Crear un puerto de recepción, como *FileSendPort*,
2. Crear una ubicación de recepción y establecer las propiedades similares para:  

    | Property | Entrada de ejemplo |
    | --- | --- |
   | Carpeta Recepción | C:\temp\In\ |
   | Máscara de archivo | *.txt |
   | Canalización | PassThruReceive |

3. En el puerto de envío que creó, establezca el **filtro** para:

    | Property | Operador | Valor |
    | --- | --- | --- |
    | BTS.ReceivePortName |  == | *FileSendPort* |

4. Cree un archivo de texto (archivo.txt) con el siguiente texto. Use este archivo de texto como el mensaje de ejemplo: 

    ```
    <Data>
      <DataID>DataID_0</DataID>
      <DataDetails>DataDetails_0</DataDetails>
    </Data>
    ```

5. Copie el mensaje de ejemplo (archivo.txt) en la carpeta de recepción. El puerto de envío envía el archivo .txt en una aplicación lógica con la URI especificada. La aplicación lógica recibe los archivos. Si usa el conector de Office 365 Outlook, su *a* dirección de correo electrónico debe recibir el correo electrónico, con el mensaje de ejemplo.

## <a name="next"></a>Siguiente
[¿Cuáles son las aplicaciones lógicas](https://azure.microsoft.com/documentation/articles/app-service-logic-what-are-logic-apps/)  

[Crear una aplicación lógica](https://azure.microsoft.com/documentation/articles/app-service-logic-create-a-logic-app/)

[Uso de adaptadores de BizTalk Server](../core/using-adapters.md)