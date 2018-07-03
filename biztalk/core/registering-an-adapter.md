---
title: Registrar un adaptador | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bc85b96e-7b7b-4131-88ec-87b419a61bc2
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ff8395a6ea80494e5fe21c7b05ebc25e6ed8c44
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985789"
---
# <a name="registering-an-adapter"></a>Registrar un adaptador
Si va a desarrollar un adaptador personalizado, puede registrarlo con BizTalk Server mediante la modificación y ejecución de uno de los archivos de Registro incluidos con el adaptador de archivo de ejemplo en el kit de desarrollo de software (SDK). O bien, puede usar el Asistente para el Registro del adaptador con el fin de crear un archivo de Registro. Este asistente está ubicado en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Utilities\AdapterRegistryWizard.  
  
> [!IMPORTANT]
> - En un equipo de 32 bits, el archivo de Registro (.reg) que genera el Asistente para el Registro del adaptador debe ejecutarse desde el símbolo del sistema.  
>   -   En un equipo de 64 bits, el archivo de Registro (.reg) que genera el Asistente para el Registro del adaptador debe ejecutarse tanto desde el símbolo del sistema de 32 bits como desde el de 64 bits.  
  
 Una vez creadas las entradas de Registro, puede agregar el adaptador en la consola de administración de BizTalk Server o mediante programación, utilizando los métodos del Instrumental de administración de Windows (WMI). En este tema se tratan las entradas de Registro y, a continuación, se muestra dónde y cómo modificar los archivos de Registro existentes del adaptador personalizado.  
  
 Para obtener instrucciones sobre cómo utilizar el Asistente para registro de adaptador, vea [asistente](../core/adapter-registry-wizard.md). Para obtener instrucciones sobre cómo modificar los archivos de registro de ejemplo incluidos en el SDK, consulte [adaptador de archivo de registro](../core/adapter-registration-file.md).  
  
## <a name="registry-keys"></a>Claves del Registro  
 Es necesario crear las siguientes entradas de Registro para implementar un adaptador:  
  
 **Ubicación de la clave del registro**  
  
```  
[HKEY_CLASSES_ROOT\CLSID\{%uuid of custom transport%}\BizTalk]  
@="BizTalk"  
  
```  
  
 **Nombre de tipo**  
  
 El nombre del tipo de adaptador identifica el tipo de adaptador del equipo de BizTalk Server. Esta clave es obligatoria para cualquier adaptador.  
  
```  
"TransportType"="MyTransportAdapter"  
  
```  
  
 **Restricciones**  
  
 Las restricciones del adaptador definen las capacidades del adaptador.  
  
 Esta clave es obligatoria para todos los adaptadores. Según el tipo de adaptador que vaya a crear, es posible que desee modificar el valor de máscara de bits de las restricciones.  
  
```  
"Constraints"=dword:00003C0b  
```  
  
 El valor que describe las capacidades del adaptador puede ser una combinación de valores que aparecen en la tabla siguiente.  
  
|Valor|Valor hexadecimal|Marca|Descripción|  
|-----------|---------------|----------|-----------------|  
|1|0x0001|eProtocolSupportsReceive|El adaptador es compatible con las operaciones de recepción.|  
|2|0x0002|eProtocolSupportsTransmit|El adaptador es compatible con las operaciones de envío.|  
|8|0x0008|eProtocolReceiveIsCreatable|El controlador de recepción del adaptador se aloja en curso.|  
|128|0x0080|eProtocolSupportsRequestResponse|El adaptador es compatible con las operaciones de solicitud-respuesta.|  
|256|0x0100|eProtocolSupportsSolicitResponse|El adaptador es compatible con las operaciones de petición-respuesta.|  
|1024|0x4000|eOutboundProtocolRequiresContextInitialization|Indica que el adaptador usa la interfaz de usuario del marco de trabajo de adaptadores para la configuración del controlador de envío.|  
|2048|0x0800|eInboundProtocolRequiresContextInitialization|Indica que el adaptador usa la interfaz de usuario del marco de trabajo de adaptadores para la configuración del controlador de recepción.|  
|4096|0x1000|eReceiveLocationRequiresContextInitialization|Indica que el adaptador usa el usuario del marco del adaptador de interfaz de configuración de la ubicación de recepción.|  
|8192|0x2000|eTransmitLocationRequiresContextInitialization|Indica que el adaptador utiliza la interfaz de usuario del marco del adaptador para la configuración de puerto de envío.|  
|16384|0x4000|eSupportsOrderedDelivery|Indica que el adaptador es compatible con la entrega de mensajes ordenada.|  
|32768|0x8000|eInitTransmitterOnServiceStart|El adaptador de envío se inicia cuando el servicio se inicia, en vez de iniciarse cuando se envía el primer mensaje.|  
|65536|0x10000|eSupport32BitOnly|Indica que el adaptador es compatible con la ejecución solo en hosts de 32 bits.|  
  
### <a name="namespace"></a>Espacio de nombres  
 Cada adaptador debe definir un espacio de nombres para sus propiedades. BizTalk Server almacena las propiedades específicas del adaptador en el contexto del mensaje en este espacio de nombres. Esta propiedad es obligatoria para todos los adaptadores.  
  
```  
"PropertyNameSpace"="namespace"  
```  
  
### <a name="aliases"></a>Alias  
 Cada adaptador puede tener un conjunto de prefijos que identifican exclusivamente el tipo de adaptador dentro de BizTalk Server. Esto permite la solución del tipo de transporte correcto al enviar un mensaje a través de un puerto de envío dinámico. El adaptador debe especificar la lista de prefijos en el momento del registro.  
  
```  
"AliasesXML"="<AdapterAliasList><AdapterAlias>sample://</AdapterAlias></AdapterAliasList>"  
```  
  
### <a name="configuration-property-pages"></a>Páginas de propiedades de configuración  
 El adaptador debe tener páginas de propiedades de configuración para configurar las ubicaciones de recepción y los puertos de envío. Cada adaptador registra sus páginas de propiedades mediante la especificación de los Id. de clase respectivos.  
  
```  
"InboundProtocol_PageProv"="{%CLSID for inbound protocol prop page%}"  
"OutboundProtocol_PageProv"="{%CLSID for outbound protocol prop page%}"  
"ReceiveLocation_PageProv"="{%CLSID for receive location prop page%}"  
"TransmitLocation_PageProv"="{%CLSID for transmit location prop page%}"  
```  
  
 Si el adaptador usa la interfaz de usuario de marco de trabajo de adaptadores para la generación de una página de propiedades, debe especificar los siguientes valores para las claves de Registro:  
  
```  
"InboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A281}"  
"OutboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A283}"  
"ReceiveLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A280}"  
"TransmitLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A282}"  
```  
  
 Tenga en cuenta que si uno de los extremos no es obligatorio (el adaptador es solo de envío o de recepción), las claves de Registro no usadas se pueden eliminar del Registro.  
  
### <a name="runtime-component-registration"></a>Registro de componente en tiempo de ejecución  
 El adaptador registra los componentes en tiempo de ejecución mediante la especificación de los Id. de clase (para COM y .NET), nombres de tipos y las rutas de ensamblado (para .NET) para los componentes en tiempo de ejecución de recepción y de envío.  
  
> [!NOTE]
>  Todos los **OutboundEngineCLSID** y **InboundEngineCLSID** las claves deben ser únicas. Para una sola fila de una base de datos, el **OutboundEngineCLSID** y **InboundEngineCLSID** puede ser el mismo.  
  
```  
"OutboundEngineCLSID"="{%CLSID of outbound transport%}"  
"InboundEngineCLSID"="{%CLSID of inbound transport%}"  
"InboundTypeName"="BizTalk.Samples.Adapters.MyReceiver"  
"OutboundTypeName"="BizTalk.Samples.Adapters.MyTransmitter"  
"InboundAssemblyPath"="C:\Program Files\MyTransport.dll"  
"OutboundAssemblyPath"="C:\Program Files\MyTransport.dll"  
```  
  
> [!NOTE]
>  Puede instalar un ensamblado de adaptador en la caché de ensamblados global y hacer referencia a ella en el archivo de Registro.  
  
### <a name="registration-of-adapter-properties-for-sso-configuration-store"></a>Registro de propiedades de adaptador para el almacén de la configuración SSO  
 El adaptador debe registrar las propiedades con la base de datos de SSO de BizTalk Server para que se pueda almacenar y recuperar las propiedades en tiempo de diseño y en tiempo de ejecución.  
  
```  
ReceiveHandlerPropertiesXML  
ReceiveLocationPropertiesXML  
SendHandlerPropertiesXML  
SendLocationPropertiesXML  
```  
  
 Estos valores contienen las definiciones (esquema) para las propiedades permitidas de las entidades correspondientes relacionadas con el adaptador, que se pueden almacenar en el almacén de configuración. Estas definiciones se guardan como una cadena XML que queda deserializada por la bolsa de propiedades que contiene los tipos de propiedades sin valores. Un valor no vacío del elemento de propiedad quiere decir que la propiedad está enmascarada. (Enmascarada significa que es de solo escritura y la API de almacén seguro no la devuelve cuando se llame en el modo administrativo; la API de almacén seguro devuelve VT_NULL para estas propiedades).  
  
### <a name="example"></a>Ejemplo  
 El adaptador de HTTP registra sus propiedades para el puerto de envío HTTP definiendo el **SendLocationPropertiesXML** clave del registro con el siguiente valor:  
  
```  
<CustomProps><Username vt="8"/><Password vt="8">Encrypted</Password><Certificate vt="8"/><RequestTimeout vt="3"/><MaxRedirects vt="3"/><ContentType vt="8"/><UseProxy vt="11"/><ProxyName vt="8"/><ProxyPort vt="3"/><ProxyUsername vt="8"/><ProxyPassword vt="8">Encrypted</ProxyPassword><UseHandlerSetting vt="11"/><AuthenticationScheme vt="8"/><UseSSO vt="11"/><AffiliateApplicationName vt="8"/></CustomProps>  
```  
  
### <a name="registration-of-the-component-as-a-transport-provider"></a>Registro del componente como proveedor de transporte  
 El adaptador debe registrarse en el atributo Categorías implementadas del Registro como proveedor de transporte. Este atributo identifica las características como consumidores del adaptador.  
  
```  
[HKEY_CLASSES_ROOT\CLSID\{%uuid of custom transport%}\Implemented Categories]  
[HKEY_CLASSES_ROOT\CLSID\{%uuid of custom transport%}\Implemented Categories\{7F46FC3E-3C2C-405B-A47F-8D17942BA8F9}]  
```  
  
## <a name="see-also"></a>Vea también  
 [Problemas de diseño del adaptador](../core/adapter-design-issues.md)