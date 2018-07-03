---
title: Componente de canalización de desarrollo de un sondeo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], probing
- IProbeMessage interface
- pipeline interfaces, IProbeMessage
ms.assetid: c3da467d-5270-4c7f-9c38-ce9989bf1b63
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0be44929609eaba5ec30a6e40c1bdda14192e351
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987365"
---
# <a name="developing-a-probing-pipeline-component"></a>Desarrollar un componente de canalización de búsqueda
Un componente de canalización (general, ensamblado o desensamblado) puede implementar la `IProbeMessage` si debe admitir la funcionalidad de búsqueda de mensajes de la interfaz. Un componente de búsqueda se usa en las etapas de canalización que tienen **FirstMatch** modo de ejecución. En tales fases, el motor de mensajería de BizTalk entrega la parte inicial del mensaje al componente para determinar si el componente identifica el formato del mensaje. Si el componente reconoce el formato, se entrega el mensaje completo al componente para que lo procese.  
  
 El **IProbeMessage** interfaz expone un método único, **sondeo**, lo que permite al componente comprobar la parte inicial del mensaje. El valor devuelto determina si se ejecuta el componente. Los siguientes pasos explican cómo el motor de mensajería de BizTalk ejecuta una fase que requiere reconocimiento:  
  
1. Si la fase no contiene ningún componente, la fase no se ejecuta y el mensaje se entrega a las fases posteriores para su procesamiento.  
  
2. Compruebe si el componente implementa la **IProbeMessage** interfaz. En caso contrario, el motor de mensajería invoca el componente. Se realiza el procesamiento de la fase y el mensaje se entrega a la siguiente fase.  
  
3. El **sondeo** se invoca el método. Si el valor devuelto es **True**, se ejecuta el componente. A continuación, se realiza el procesamiento de la fase y el mensaje se entrega a una fase siguiente.  
  
4. El motor de mensajería obtiene el siguiente componente de la fase. Si no hay más componentes y ninguno de ellos se ha ejecutado, genera un error que indica que se ha producido un error en el procesamiento de canalización. Si no hay más componentes y se ha ejecutado como mínimo un componente, se lleva a cabo el procesamiento.  
  
   Si una fase no necesita reconocimiento (por ejemplo, el modo de ejecución es **todas**), el motor de mensajería invoca el componente sin consultar primero para la **IProbeMessage** interfaz y una llamada a la **Sondeo** método.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar un componente de canalización generales](../core/developing-a-general-pipeline-component.md)   
 [Desarrollar un componente de canalización de ensamblado](../core/developing-an-assembling-pipeline-component.md)   
 [Desarrollar un componente de canalización de desensamblado](../core/developing-a-disassembling-pipeline-component.md)   
 [Informes de errores de componentes de canalización](../core/reporting-errors-from-pipeline-components.md)   
 [Configurar componentes de canalización nativos](../core/configuring-native-pipeline-components.md)   
 [Implementación de componentes de canalización](../core/deploying-pipeline-components.md)