---
layout: page
title: About
permalink: /about/
---


Lorem ipsum dolor sit amet, simul pertinax nam ea, qui omittam inimicus ex. Id audiam expetenda nec, qui no debet zril suscipiantur. Vim error salutatus id. Ut ignota delicatissimi vel.

Ut vim facilisis pertinacia, soluta laboramus sadipscing mel et, nam inimicus imperdiet vituperata ei. Duo cu nulla patrioque hendrerit, nullam maluisset sententiae no est, ad per sale aeterno eruditi. Eu duis mediocrem duo, ad per etiam essent percipit. Ex eos wisi omnesque, duo debitis vituperatoribus cu.

Id quas admodum sed, te sed legimus deterruisset. Cum amet eleifend salutatus ei. Mea utroque adipiscing ut. Eum cu persius alienum, ius graece scaevola ea, no per feugiat abhorreant. Ridens efficiantur eos ex, vide elitr definitionem nam ad. Has te luptatum quaestio adolescens.

Possit meliore posidonium et mea, ea sea illum dolor, noster bonorum sit ne. Usu id nihil fastidii deterruisset. Meliore recteque mel et, aliquam maluisset quo et, nisl sonet eu est. His ex meis quando dolorem, mea in habeo utinam appareat. Est hinc libris et. Id mel sumo accumsan pericula.

His fugit pericula in. Ea usu magna facer detracto, eam eruditi eleifend pertinacia ea. Ius ea omnium bonorum, expetenda consetetur id usu. Ei posse offendit insolens sed. Et tale sanctus percipitur duo, qui commodo accumsan omnesque ei.

<!-- This is the base Jekyll theme. You can find out more info about customizing your Jekyll theme, as well as basic Jekyll usage documentation at [jekyllrb.com](http://jekyllrb.com/)

You can find the source code for the Jekyll new theme at:
{% include icon-github.html username="jglovier" %} /
[jekyll-new](https://github.com/jglovier/jekyll-new)

You can find the source code for Jekyll at
{% include icon-github.html username="jekyll" %} /
[jekyll](https://github.com/jekyll/jekyll) -->


Pie Chart

<body>
    <script src="/scripts/dist/Chart.bundle.js"></script>
    <script src="http://cdnjs.cloudflare.com/ajax/libs/jquery/2.1.3/jquery.min.js"></script>
    <div id="canvas-holder" style="width:50%">
        <canvas id="chart-area" width="300" height="300" />
    </div>
    <button id="randomizeData">Randomize Data</button>
    <button id="addDataset">Add Dataset</button>
    <button id="removeDataset">Remove Dataset</button>
    <script>
    var randomScalingFactor = function() {
        return Math.round(Math.random() * 100);
    };
    var randomColorFactor = function() {
        return Math.round(Math.random() * 255);
    };
    var randomColor = function(opacity) {
        return 'rgba(' + randomColorFactor() + ',' + randomColorFactor() + ',' + randomColorFactor() + ',' + (opacity || '.3') + ')';
    };

    var config = {
        type: 'pie',
        data: {
            datasets: [{
                data: [
                    randomScalingFactor(),
                    randomScalingFactor(),
                    randomScalingFactor(),
                    randomScalingFactor(),
                    randomScalingFactor(),
                ],
                backgroundColor: [
                    "#F7464A",
                    "#46BFBD",
                    "#FDB45C",
                    "#949FB1",
                    "#4D5360",
                ],
            }, {
                data: [
                    randomScalingFactor(),
                    randomScalingFactor(),
                    randomScalingFactor(),
                    randomScalingFactor(),
                    randomScalingFactor(),
                ],
                backgroundColor: [
                    "#F7464A",
                    "#46BFBD",
                    "#FDB45C",
                    "#949FB1",
                    "#4D5360",
                ],
            }, {
                data: [
                    randomScalingFactor(),
                    randomScalingFactor(),
                    randomScalingFactor(),
                    randomScalingFactor(),
                    randomScalingFactor(),
                ],
                backgroundColor: [
                    "#F7464A",
                    "#46BFBD",
                    "#FDB45C",
                    "#949FB1",
                    "#4D5360",
                ],
            }],
            labels: [
                "Red",
                "Green",
                "Yellow",
                "Grey",
                "Dark Grey"
            ]
        },
        options: {
            responsive: true
        }
    };

    window.onload = function() {
        var ctx = document.getElementById("chart-area").getContext("2d");
        window.myPie = new Chart(ctx, config);
    };

    $('#randomizeData').click(function() {
        $.each(config.data.datasets, function(i, piece) {
            $.each(piece.data, function(j, value) {
                config.data.datasets[i].data[j] = randomScalingFactor();
                config.data.datasets[i].backgroundColor[j] = randomColor(0.7);
            });
        });
        window.myPie.update();
    });

    $('#addDataset').click(function() {
        var newDataset = {
            backgroundColor: [randomColor(0.7), randomColor(0.7), randomColor(0.7), randomColor(0.7), randomColor(0.7)],
            data: [randomScalingFactor(), randomScalingFactor(), randomScalingFactor(), randomScalingFactor(), randomScalingFactor()]
        };

        config.data.datasets.push(newDataset);
        window.myPie.update();
    });

    $('#removeDataset').click(function() {
        config.data.datasets.splice(0, 1);
        window.myPie.update();
    });
    </script>
</body>


