---
title: Referencia de línea de comandos de BTSWebSvcPub | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5e19dd4d-9f2c-4a17-9437-8701e1c274fb
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c9993092c0d798ae2d47f614a24da21c3a2df62
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
---
# <a name="btswebsvcpub-command-line-reference"></a>Referencia de línea de comandos de BTSWebSvcPub
Esta sección proporciona información de referencia para la herramientas de línea de comandos de BTSWebSvcPub incluidas en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Puede utilizar BTSWebSvcPub para crear servicios Web (.asmx) para publicar orquestaciones mediante los servicios Web como se muestra a continuación:  
  
## <a name="usage"></a>Uso  
 **BTSWebSvcPub PathName [-ubicación:** *valor* **] [-sobrescribir] [-Anonymous]**  
  
 **[-Name:** *value* **] [-Namespace:** *value* **] [-TargetNamespace:** *value* **]**  
  
 **[-UnknownHeaders[** *+* **&#124;** *-* **]] [-SingleSignOn[** *+* **&#124;** *-* **]] [-ParameterStyle:** *value* **]**  
  
 **[-ConformanceClaims:** *value* **] [-ForceRequestResponse:** *value* **] [-ReceiveLocation]**  
  
 **[-ApplicationName:** *valor* **]**  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Obligatorio|Description|  
|---------------|--------------|-----------------|  
|**Ruta de acceso**|Sí|Ruta de acceso y nombre de archivo de ensamblado de BizTalk (*.dll) o la descripción del servicio web (\*.xml) archivo.|  
|**-Ubicación**|no|Ubicación de publicación. (Sintaxis:"http://host[:puerto]/ruta")|  
|**-Overwrite**|no|Sobrescribir la ubicación especificada.|  
|**-Anonymous**|no|Permitir el acceso anónimo al servicio Web.|  
|**-Name**|no|Nombre del ensamblado (archivos .sln y .dll) y de la solución que contiene el servicio Web.|  
|**-Namespace**|no|Espacio de nombres predeterminado del código del servicio Web.|  
|**-Targetnamespace**|no|Espacio de nombres de destino del servicio Web. (Ejemplo:'http://www.northwindtraders.com')|  
|**-UnknownHeaders**|no|Admitir encabezados SOAP desconocidos.|  
|**-SinglesSignon**|no|Admitir encabezados de inicio de sesión único SOAP de SharePoint Portal Server.|  
|**-ParameterStyle**|no|SoapParameterStyle para mensajes: "Default", "Bare" o "Wrapped".|  
|**-ConfirmanceClaims**|no|Notificación de interoperabilidad de servicios Web (WSI): "None" o "Perfilbásico1_1".|  
|**-ForceRequestResponse**|no|Exponer operaciones unidireccionales de BizTalk como métodos Web de solicitud-respuesta.|  
|**-ReceiveLocation**|no|Cree ubicaciones de recepción en la aplicación de BizTalk especificada.|  
|**-ApplicationName**|no|Nombre de la aplicación de BizTalk en la que se crean ubicaciones de recepción. Si no se especifica, se utiliza la aplicación de BizTalk predeterminada.|  
  
## <a name="sample"></a>Ejemplo  
 BTSWebSvcPub.exe "MyAssembly.dll" -Location: http://localhost/MyVdir  
  
 -Overwrite  
  
## <a name="remarks"></a>Comentarios  
 Los nombres de parámetros no distinguen entre mayúsculas y minúsculas, y se pueden abreviar. Los valores de parámetros distinguen entre mayúsculas y minúsculas.  
  
## <a name="see-also"></a>Vea también  
 [Cómo usar el Asistente para publicar los servicios Web de BizTalk para publicar una orquestación como servicio Web](../core/publish-orchestration-as-web-service--biztalk-web-services-publishing-wizard.md)