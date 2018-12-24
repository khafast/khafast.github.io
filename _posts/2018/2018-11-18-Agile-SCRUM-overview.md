---
layout: post
title: Overview Agile & SCRUM
category: [agile, scrum]
tags: [agile, scrum]
---
---
<script src="../../assets/js/js2flowchart.js"></script>
<script>const { convertCodeToSvg } = window['js2flowchart'];</script>
---

# mermaid

## Overview

<div id="jsAgileDescription" style="display:none">
    let envision = function (keyLessonLearn) {
        // this is inception phase
        requirements = "?";
        keyStakeHolders = { "who":"assigned to...", 
                            "who":"assigned to..."};
        schedule = new Schedule(keyStakeHolders, requirements);
        cost = calculateCost(schedule, otherFactors);
        risk = estimateRisk(schedule, cost, otherFactors);

    }

    let construction = function (requirements, cost, risk, schedule) {
        // this is speculative phase
        for(stakeHolder in keyStakeHolders){
            // {  "Req.1":"todo1?, todo2?", "Req.2":"todo3?, todo4?";
            [todo, milestone] = stakeHolder.analyze(risk, requirements);
            todoList.add(todo, milestone);
            cost.update(milestone.cost);
        }
        projectPlan(cost, risk, schedule, todoList);
    }

    let explore = function (requirements, todoList) {
         // this is transitional stage
         releaseMileStones = {}
         todoList = {"todo1": "how1?", "todo2": "how2?"}
         needContinue = reportStatusToScrum()

         while(needContinue && todoList.length > 0) {
            actionItem = todoList.pop()
            devResult = execute(actionItem);
            [isWrong, actionItem] = test(requirements, devResult);
            if(isWrong) {
                todoList.add(actionItem);
            }
            needContinue = reportStatusToScrum()
         }
    }

    function production() {
        // this is adaption phase
        reviewResultOfTransitionalPhase();
        assessCurrentSituation();
        assessPerformanceOfProjectResults();
        reviewFeedbakFromKeyStakeHolders();

        while(needContinue) {
            [status, enhancementRequest] = customerSupport(); // Installing, or operating new system
            needContinue = reportStatusToScrum(status, enhancementRequest);
            
            if(isMandatory(enhancementRequest)) {
                updateSystem(enhancementRequest)
            } else {
                projectBacklog.add(enhancementRequest)
            }
        }
    }

    function retire() {
        keyLessonLearn.extend( {"?":"?", "?":"?"})
    }

    function main() {
        envision();
        construction();
        explore();
        production();
        retire();
    }
</div>
<div><p id="svgImageAgile"></p></div>

<script>
    var code = document.getElementById('jsAgileDescription').textContent;
    document.getElementById('svgImageAgile').innerHTML = convertCodeToSvg(code);
</script>

## Ref
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTkzNTkyNzE2M119
-->