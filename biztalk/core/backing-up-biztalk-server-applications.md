---
title: Copia de seguridad de aplicaciones de BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b51e3ae6-08ed-48ca-8977-13f46144a5fa
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d125a1430aa2d044abba7632fa31a9c89f2bc50
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230380"
---
# <a name="backing-up-biztalk-server-applications"></a>Realizar una copia de seguridad de aplicaciones de BizTalk Server
Para asegurarse de que podrá recuperar el sistema de BizTalk Server después de que se haya producido un error de hardware, es importante contar con buenas copias de seguridad. Para mantener las copias de seguridad, se aconseja exportar las aplicaciones de BizTalk a un servidor remoto y realizar una copia de seguridad de esas aplicaciones.  
  
 Más tarde, cuando restaure las bases de datos de BizTalk Server y vuelva a instalar BizTalk Server, podrá importar estas aplicaciones. Para obtener más información acerca de cómo exportar e importar aplicaciones, consulte [implementar y administrar aplicaciones de BizTalk](../core/deploying-and-managing-biztalk-applications.md).  
  
 Debería exportar los archivos .msi de todas las aplicaciones BizTalk que se han implementado en el equipo y guardarlos en la ubicación de copias de seguridad (en un servidor distinto). Los archivos .msi permiten volver a instalar los recursos que requiere BizTalk Server una vez que se ha recuperado el equipo de destino. Debería asegurarse de que los archivos .msi incluyen todos los recursos necesarios y de que se especifican las acciones que se van a realizar en la instalación de los archivos .msi para estos recursos. Si la aplicación de BizTalk depende de cualquier ensamblado de usuario o de otros DLL que no están incluidos en los archivos .msi, se deben realizar copias de seguridad de ellos por separado.  
  
 El proceso de exportación de la aplicación es el mismo para los escenarios de enrutamiento por contenidos que para los que tienen orquestaciones. Este proceso se debería repetir siempre que se cambien las aplicaciones de BizTalk. Para obtener más información, consulte [cómo exportar una aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md).  
  
## <a name="see-also"></a>Vea también  
 [Realizar una copia de seguridad de un equipo que ejecuta BizTalk Server](../core/backing-up-a-computer-running-biztalk-server.md)