---
redirect_url: /biztalk/core/architecture-of-biztalk-adapter-for-peoplesoft-enterprise/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: a277c5f5588a9455119b96f7c600dbadccffb8ac
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014539"
---
# <a name="peoplesoft-enterprise-requirements"></a>Requisitos de PeopleSoft Enterprise

## <a name="send-handler-requirements"></a>Requisitos del controlador de envío  
 El adaptador de Microsoft BizTalk para PeopleSoft Enterprise contiene una interfaz de componente personalizado (CI) y proporciona acceso a ella a través de un API Java. Un objeto CI personalizado, `GET_CI_INFO`, se implementa en el sistema PeopleSoft mediante las herramientas de PeopleSoft, para proporcionar informar de metadatos, necesaria para el adaptador de BizTalk para PeopleSoft Enterprise. Para obtener más información, consulte [adaptadores instalar aplicaciones empresariales](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md).  
  
 La carga de la interfaz de componente personalizado es una única repetición. Este archivo, `GET_CI_INFO.pc`, se instala con el producto y debe instalarse antes de usar el adaptador para buscar CI. Debe tener acceso a PeopleSoft Application Designer. La aplicación del Diseñador de aplicaciones no deben ser en el equipo de servidor BizTalk Server. Use Application Designer para cargar el CI personalizado en el equipo de PeopleSoft en el que está buscando.  
  
 Debe tener acceso al equipo de PeopleSoft porque debe establecer la variable de entorno CLASSPATH (o establecer la información en el **propiedades de transporte** pantalla) para que señale a de PeopleSoft `PSJOA/psjoa.jar` archivo.  
  
## <a name="see-also"></a>Vea también  
 [Introducción](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md)   
 