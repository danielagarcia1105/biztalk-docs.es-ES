---
title: Incorporación de un nuevo proceso de interfaz de socio comercial | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, PIP schemas
- PIP schemas
- PIP schemas, deploying
- PIP schemas, downloading
- creating, PIP schemas
- PIP schemas, creating
ms.assetid: 6a5fcbcb-c6aa-40c0-bcca-dd0c391e7f42
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bf80c8bb577f4ddc8aec3282805714a830c7d23
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963594"
---
# <a name="incorporating-a-new-partner-interface-process"></a>Incorporación de un nuevo proceso de interfaz de socio comercial
Puede incorporar un nuevo esquema de proceso de interfaz de socio (PIP) RosettaNet en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] ensamblados. Para ello:  
  
-   Descargar el esquema PIP desde el sitio RosettaNet Web en [http://go.microsoft.com/fwlink/?linkid=33859](http://go.microsoft.com/fwlink/?linkid=33859).  
  
-   Implementar el esquema para [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] como parte de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Rnpip ensamblado o como parte de otro [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] ensamblado. Para obtener más información, consulte [BTARN extender a una PIP nueva](../../adapters-and-accelerators/accelerator-rosettanet/extending-btarn-with-a-new-pip.md).  
  
-   Crear un nuevo valor de configuración de proceso en el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] consola de administración. Para obtener más información, consulte [cómo crear o editar una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).  
  
 El esquema descargado generalmente está en formato de .dtd, con una especificación de PIP acompañamiento de la organización RosettaNet como un archivo .doc. El proceso de la extensión de la canalización para usar el nuevo esquema incluye la conversión del archivo de .dtd PIP en un archivo .xsd.  
  
 Al instalar [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK incluye una serie de esquemas XSD. Puede encontrar los esquemas en el \< *unidad*\>: \Program BizTalk \<versión\> Accelerator for RosettaNet\SDK\Schemas carpeta. BTARN crea estos esquemas a un archivo RNPIPs.dll. Si tiene que cambiar uno de estos esquemas, debe abrir el proyecto Rnpip en la misma carpeta, cambiar el esquema en el Editor de BizTalk y, a continuación, vuelva a compilar y volver a implementar el ensamblado. Después de volver a implementar el archivo RNPIPs.dll, debe volver a implementar la canalización que utiliza el esquema. Puede utilizar este proceso para incorporar un nuevo esquema en BTARN, pero es más fácil ampliar la canalización para incluir el nuevo esquema.  
  
### <a name="to-obtain-the-pip-schema"></a>Para obtener el esquema PIP  
  
-   En Internet Explorer, vaya al sitio RosettaNet Web en [http://go.microsoft.com/fwlink/?linkid=33859](http://go.microsoft.com/fwlink/?linkid=33859).  
  
## <a name="see-also"></a>Vea también  
 [Extensión de BTARN con un PIP nuevo](../../adapters-and-accelerators/accelerator-rosettanet/extending-btarn-with-a-new-pip.md)