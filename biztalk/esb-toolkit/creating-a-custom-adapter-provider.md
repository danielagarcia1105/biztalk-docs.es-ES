---
title: Crear un proveedor de adaptador personalizado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb93acf8-fd9d-4315-8690-f0c152a954b5
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f70855621f03011c92be7b04b844122d98be48f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974282"
---
# <a name="creating-a-custom-adapter-provider"></a>Crear un proveedor de adaptador personalizado
Una vez ejecutada una resolución, tal como se describe en las secciones anteriores, el servicio de resolución dinámica comprueba si el resultado es un punto de conexión (no una transformación). Si es un punto de conexión, el servicio crea instancias el Administrador de adaptador, que es una instancia de la **AdapterMgr** clase.  
  
 El Administrador de adaptador valida y corrige el tipo de transporte y la ubicación de transporte de salida. Si el tipo de transporte se sigue sin resolverse, y si la dirección URL comienza con "http" o "https", el Administrador de adaptador establece el tipo de transporte para "WCF-WSHttp".  
  
 A continuación, el Administrador de adaptador comprueba que el tipo de transporte equivale a un adaptador de Microsoft BizTalk Server válido y, a continuación, devuelve su espacio de nombres de propiedad. Este proceso se ejecuta sólo una vez para todos los adaptadores y almacena los resultados en una caché para evitar consultas repetidas otros mensajes entrantes que utilizan el mismo adaptador.  
  
 El Administrador de adaptador usa el tipo de transporte (sin el "**://**" sufijo) para determinar el proveedor del adaptador adecuado. Un proveedor de adaptador es un ensamblado personalizado que debe implementar la **IAdapterProvider** interfaz. El proveedor del adaptador utiliza las propiedades de la **resolución** estructura en la **diccionario** instancia generada por la resolución para establecer todas las propiedades específicas del protocolo del mensaje que permite la Motor de tiempo de ejecución de Microsoft BizTalk Server para realizar la resolución dinámica.  
  
 Como con la resolución (descrita en la sección anterior), el mecanismo de resolución dinámica utiliza las entradas en el archivo de configuración Esb.config para encontrar proveedores del adaptador. El siguiente XML muestra la sección del archivo de configuración.  
  
```xml  
<adapterProviders cacheManager= "Adapter Providers Cache Manager"  absoluteExpiration="3600">  
     <adapterProvider name="WCF-WSHttp" type="Microsoft.Practices.ESB.Adapter.WcfWSHttp.AdapterProvider, Microsoft.Practices.ESB.Adapter.WcfWSHttp, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22" moniker="Http,Https" />  
     <adapterProvider name="WCF-BasicHttp" type="Microsoft.Practices.ESB.Adapter.WcfBasicHttp.AdapterProvider, Microsoft.Practices.ESB.Adapter.WcfBasicHttp, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22" moniker="Http,Https" />  
     <adapterProvider name="WCF-Custom" type="Microsoft.Practices.ESB.Adapter.WcfCustom.AdapterProvider, Microsoft.Practices.ESB.Adapter.WcfCustom, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22" moniker="mssql" />  
     <adapterProvider name="SMTP" type="Microsoft.Practices.ESB.Adapter.SMTP.AdapterProvider, Microsoft.Practices.ESB.Adapter.SMTP, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22" moniker="smtp" />  
     <adapterProvider name="FTP" type="Microsoft.Practices.ESB.Adapter.FTP.AdapterProvider, Microsoft.Practices.ESB.Adapter.FTP, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22">  
          <adapterConfig>  
               <add name="DefaultUsername" value="anonymous" />  
               <add name="DefaultPassword" value="" />  
          </adapterConfig>  
     </adapterProvider>  
     <adapterProvider name="MQSeries" type="Microsoft.Practices.ESB.Adapter.MQSeries.AdapterProvider, Microsoft.Practices.ESB.Adapter.MQSeries, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22" moniker="MQS" adapterAssembly="MQSeries, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
     <adapterProvider name="FILE" type="Microsoft.Practices.ESB.Adapter.FILE.AdapterProvider, Microsoft.Practices.ESB.Adapter.FILE, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22" moniker="File" />  
</adapterProviders>  
```  
  
## <a name="creating-a-custom-adapter-provider"></a>Crear un proveedor de adaptador personalizado  
 El Administrador de adaptador (una instancia de la **AdapterMgr** clase) busca el proveedor del adaptador en los archivos de configuración y carga el ensamblado adecuado. El mecanismo de resolución dinámica almacena en caché cargadas todas las implementaciones concretas de la **IAdapterProvider** interfaz para evitar la lectura repetida de información de configuración y cuando usan varios mensajes entrantes de carga de ensamblados el mismo proveedor de adaptador.  
  
 Por último, se ejecuta el Administrador de adaptador el **SetEndPoint** método de la implementación concreta de la **IAdapterProvider** interfaz y el componente de canalización devuelve el mensaje a BizTalk Base de datos de cuadro de mensaje.  
  
 **Para crear un proveedor de adaptador personalizado**  
  
1.  Crear un ensamblado que se deriva de la **BaseAdapterProvider** clase base y contiene un **SetEndPoint** método que establece el punto de conexión en las propiedades de contexto del mensaje.  
  
2.  Registrar el proveedor del adaptador, éste se agrega a los archivos de configuración de Esb.config con un  **\<adapterProvider\>**  elemento con un nombre para el adaptador como la **nombre** atributo, el nombre completo de la clase como el **tipo** de atributo, el moniker como el **moniker** atributo (varios valores deben estar separados por una coma) y, opcionalmente, el ensamblado de la adaptador real como el **adapterAssembly** atributo.  
  
3.  Registrar el nuevo ensamblado en la caché global de ensamblados.