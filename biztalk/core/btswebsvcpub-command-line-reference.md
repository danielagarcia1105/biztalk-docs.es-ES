---
title: "Referencia de línea de comandos de BTSWebSvcPub | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5e19dd4d-9f2c-4a17-9437-8701e1c274fb
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c9993092c0d798ae2d47f614a24da21c3a2df62
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="btswebsvcpub-command-line-reference"></a>Referencia de línea de comandos de BTSWebSvcPub
Esta sección proporciona información de referencia para la herramientas de línea de comandos de BTSWebSvcPub incluidas en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Puede utilizar BTSWebSvcPub para crear servicios Web (.asmx) para publicar orquestaciones mediante los servicios Web como se muestra a continuación:  
  
## <a name="usage"></a>Uso  
 **BTSWebSvcPub PathName [-ubicación:** *valor* **] [-sobrescribir] [-Anonymous]**  
  
 **[-Name:** *valor* **] [-Namespace:** *valor* **] [-TargetNamespace:** *valor* **]**  
  
 **[-UnknownHeaders [**  *+*  **&#124;**  *-*  **]] [-SingleSignOn [**  *+*  **&#124;**  *-*  **]] [-ParameterStyle:** *valor* **]**  
  
 **[-ConformanceClaims:** *valor* **] [-ForceRequestResponse:** *valor* **] [-ReceiveLocation]**  
  
 **[-ApplicationName:** *valor* **]**  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Necesario|Description|  
|---------------|--------------|-----------------|  
|**PathName**|Sí|Ruta de acceso y nombre de archivo de ensamblado de BizTalk (*.dll) o la descripción del servicio web (\*.xml) archivo.|  
|**-Ubicación**|No|Ubicación de publicación. (Sintaxis:"http://host[:puerto]/ruta")|  
|**-Sobrescribir**|No|Sobrescribir la ubicación especificada.|  
|**-Anónimo**|No|Permitir el acceso anónimo al servicio Web.|  
|**-Nombre**|No|Nombre del ensamblado (archivos .sln y .dll) y de la solución que contiene el servicio Web.|  
|**-Namespace**|No|Espacio de nombres predeterminado del código del servicio Web.|  
|**-Targetnamespace**|No|Espacio de nombres de destino del servicio Web. (Ejemplo: 'http://www.northwindtraders.com')|  
|**-UnknownHeaders**|No|Admitir encabezados SOAP desconocidos.|  
|**-SinglesSignon**|No|Admitir encabezados de inicio de sesión único SOAP de SharePoint Portal Server.|  
|**-ParameterStyle**|No|SoapParameterStyle para mensajes: "Default", "Bare" o "Wrapped".|  
|**-ConfirmanceClaims**|No|Notificación de interoperabilidad de servicios Web (WSI): "None" o "Perfilbásico1_1".|  
|**-ForceRequestResponse**|No|Exponer operaciones unidireccionales de BizTalk como métodos Web de solicitud-respuesta.|  
|**-ReceiveLocation**|No|Cree ubicaciones de recepción en la aplicación de BizTalk especificada.|  
|**-El nombre de aplicación**|No|Nombre de la aplicación de BizTalk en la que se crean ubicaciones de recepción. Si no se especifica, se utiliza la aplicación de BizTalk predeterminada.|  
  
## <a name="sample"></a>Ejemplo  
 BTSWebSvcPub.exe "MyAssembly.dll" -Location: http://localhost/MyVdir  
  
 -Overwrite  
  
## <a name="remarks"></a>Comentarios  
 Los nombres de parámetros no distinguen entre mayúsculas y minúsculas, y se pueden abreviar. Los valores de parámetros distinguen entre mayúsculas y minúsculas.  
  
## <a name="see-also"></a>Vea también  
 [Cómo usar el Asistente para publicar los servicios Web de BizTalk para publicar una orquestación como servicio Web](../core/publish-orchestration-as-web-service--biztalk-web-services-publishing-wizard.md)