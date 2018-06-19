---
title: Exportar aplicaciones de BizTalk, los enlaces y directivas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, exporting
- exporting, policies
- bindings, exporting
- exporting, applications
- applications, exporting
- exporting, bindings
ms.assetid: ac101206-be49-47c9-a354-4f39e8b77acf
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d6df445b0fefc132940a736870d66c62329ce60
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245812"
---
# <a name="exporting-biztalk-applications-bindings-and-policies"></a>Exportar aplicaciones, enlaces y directivas de BizTalk
En esta sección se describe cómo exportar una aplicación, enlaces o directivas de BizTalk. Puede exportar algunos o todos los artefactos que contiene una aplicación de BizTalk, o bien puede exportar únicamente sus enlaces o directivas. Al exportar una aplicación se crea un archivo (.msi) de Windows Installer que contiene los artefactos de la aplicación seleccionados para que se exportaran. Al exportar enlaces o directivas se crea un archivo .xml de esos enlaces o directivas. Para obtener información general acerca de este proceso, consulte [¿qué ocurre cuando los artefactos se exportan](../core/what-happens-when-artifacts-are-exported.md).  
  
 Puede importar un archivo .msi de aplicación en otro grupo de BizTalk para crear una nueva aplicación que contenga los artefactos de la aplicación de ese grupo. Puede importar un archivo .xml de enlaces o directivas en otra aplicación de BizTalk para utilizar esos enlaces o directivas. Se describe cómo importar artefactos en [importar aplicaciones de BizTalk, los enlaces y directivas](../core/importing-biztalk-applications-bindings-and-policies.md).  
  
> [!IMPORTANT]
>  Almacene los archivos de enlaces en una ubicación segura, ya que pueden contener datos económicos importantes, como información de conectividad y de configuración.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo exportar una aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md)  
  
-   [Exportar enlaces](../core/exporting-bindings6.md)  
  
-   [Cómo exportar una directiva](../core/how-to-export-a-policy.md)