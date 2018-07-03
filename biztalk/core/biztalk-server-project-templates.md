---
title: Plantillas de proyecto de Visual Studio | Microsoft Docs
description: Describe el .btproj, BPEL y plantillas de Visual Studio .btaproj usadas por BizTalk Server
ms.custom: ''
ms.date: 11/07/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2b3d494-db80-4314-afcd-d08d5a26e211
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14d35eb4f12bdb7a66da28d94c8fabd33b073127
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018376"
---
# <a name="biztalk-server-project-templates"></a>Plantillas de proyecto de BizTalk Server

## <a name="overview"></a>Información general
Al instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], la instalación agrega la carpeta de proyectos de BizTalk para el **nuevo proyecto** cuadro de diálogo. La carpeta de proyectos de BizTalk contiene plantillas para crear un proyecto vacío de servidor BizTalk Server, el proyecto de importación BPEL de BizTalk Server y un proyecto de aplicación de BizTalk Server.

## <a name="available-templates"></a>Plantillas disponibles
En la tabla siguiente se describe estas plantillas de proyecto.  


|                     Use                      |                                                                                                                                                                   Para                                                                                                                                                                   |
|---------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         **Proyecto vacío de servidor BizTalk Server**          |                                                                                                                                                  Crea un nuevo proyecto vacío de servidor BizTalk Server.                                                                                                                                                   |
|      **Proyecto de importación BPEL de servidor BizTalk Server**       |                                                                                      Importa archivos de lenguaje de ejecución de procesos empresariales (BPEL), lenguaje de descripción de servicios Web (WSDL) o lenguaje de definición de esquemas XML (XSD) a un proyecto de BizTalk.                                                                                       |
| **Proyecto de aplicación de BizTalk Server (.btaproj)** | A partir de [!INCLUDE[bts2016](../includes/bts2016-md.md)] [Feature Pack 1](../core/configure-the-feature-pack.md), o una versión posterior. <br/><br/>Se usa para implementar y actualizar automáticamente aplicaciones con Visual Studio Team Services (VSTS). El proyecto contiene un `BizTalkServerInventory.json` archivo que se utiliza VSTS durante la implementación. |

## <a name="see-also"></a>Vea también  
 [Trabajar con proyectos de BizTalk](../core/working-with-biztalk-projects.md)
