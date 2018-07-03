---
title: Incorporación de un nuevo proceso de interfaz de socio | Microsoft Docs
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
ms.openlocfilehash: 558509c85da8de044bad1b320f3beb31c27e006b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969797"
---
# <a name="incorporating-a-new-partner-interface-process"></a>Incorporación de un nuevo proceso de interfaz de socio
Puede incorporar un nuevo esquema de proceso de interfaz de socio (PIP) RosettaNet en Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] ensamblados. Para ello:  
  
- Descargar el esquema PIP desde el sitio RosettaNet Web en [ http://go.microsoft.com/fwlink/?linkid=33859 ](http://go.microsoft.com/fwlink/?linkid=33859).  
  
- Implementar el esquema para [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] como parte de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Rnpip ensamblado o como parte de otro [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] ensamblado. Para obtener más información, consulte [BTARN extender con un PIP nuevo](../../adapters-and-accelerators/accelerator-rosettanet/extending-btarn-with-a-new-pip.md).  
  
- Crear una nueva opción de configuración de proceso en el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] consola de administración. Para obtener más información, consulte [cómo crear o editar una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).  
  
  El esquema descargado suele estar en formato .dtd, con una especificación de PIP que lo acompaña de la organización RosettaNet como un archivo .doc. El proceso de extensión de la canalización para utilizar el nuevo esquema incluye convertir el archivo .dtd PIP en un archivo .xsd.  
  
  Al instalar [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK incluye una serie de esquemas XSD. Puede encontrar esos esquemas en el \< *unidad*\>: \Program Files\Microsoft BizTalk \<versión\> Accelerator for RosettaNet\SDK\Schemas carpeta. BTARN, estos esquemas basa en un archivo RNPIPs.dll. Si tiene que cambiar uno de estos esquemas, debe abrir el proyecto Rnpip en la misma carpeta, cambiar el esquema en el Editor de BizTalk y, a continuación, volver a compilar e implementar el ensamblado. Después de volver a implementar el archivo RNPIPs.dll, debe volver a implementar la canalización que utiliza el esquema. Este proceso podría usarse para incorporar un nuevo esquema en BTARN, pero es más fácil de ampliar la canalización para incluir el nuevo esquema.  
  
### <a name="to-obtain-the-pip-schema"></a>Para obtener el esquema PIP  
  
-   En Internet Explorer, vaya al sitio RosettaNet Web en [ http://go.microsoft.com/fwlink/?linkid=33859 ](http://go.microsoft.com/fwlink/?linkid=33859).  
  
## <a name="see-also"></a>Vea también  
 [Extensión de BTARN con un PIP nuevo](../../adapters-and-accelerators/accelerator-rosettanet/extending-btarn-with-a-new-pip.md)