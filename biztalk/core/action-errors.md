---
title: Errores de acción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87cf0a5b-d1dd-4807-9660-e8a8b7012b40
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3cb63e90f85c830c30524b3adc1e3b0d86ab8b7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997277"
---
# <a name="action-errors"></a>Errores de acción
En esta sección se incluye información detallada para diagnosticar y resolver errores de acciones de WCF.  
  
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                     |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                  |
| Versión del producto |                                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                              |
|    Identificador del evento     |                                                                          0                                                                          |
|  Origen del evento   |                                                                          0                                                                          |
|    Componente    |                                                                          0                                                                          |
|  Nombre simbólico  |                                                                          0                                                                          |
|  Texto del mensaje   | Una acción única no puede contener caracteres de nueva línea. Quite todos los caracteres de nueva línea, o use la sintaxis de asignación de acción para especificar varias acciones. |
  
## <a name="explanation"></a>Explicación  
 Este error indica que la propiedad de acción de un puerto de envío contiene un carácter de nueva línea, que no está permitido.  
  
> [!NOTE]
>  Esta restricción no se aplica cuando la acción se define como una asignación.  
  
## <a name="user-action"></a>Acción del usuario  
 Use el procedimiento siguiente para corregir la propiedad de la acción.  
  
 
1. Abra **administración de BizTalk Server**.  
  
2. En la raíz de consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**y expanda **aplicaciones**.  
  
3. Localice la aplicación y, a continuación, el transporte.  
  
4. Haga clic con el botón secundario en el nombre del transporte.  
  
5. Seleccione **propiedades**.  
  
6. En el puerto **tipo** lista, seleccione el puerto correcto.  
  
7. Seleccione **Configurar**.  
  
8. En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, seleccione el **General** ficha.  
  
9. En el **encabezado Action de SOAP** sección, quite el carácter de nueva línea desde el **acción** cuadro de texto.  

## <a name="more-good-info"></a>Obtener más información buena  
 Para obtener más información sobre las acciones, vea [especificar acciones SOAP para adaptadores de envío de WCF](../core/specifying-soap-actions-for-wcf-send-adapters.md)