$(document).ready(function() {
        var typed = new Typed('#type', {
            strings: ["Simple HTML5 example for RESTUL api calls"],
            typeSpeed: 30
        });

        $.ajax({
            url: "https://jsonplaceholder.typicode.com/posts/10",
            method: 'GET'
        }).then(function(data) {
            $('#get').append(JSON.stringify(data, null, 4));
        });

        $.ajax('http://jsonplaceholder.typicode.com/posts', {
            method: 'POST',
            data: {
                title: 'foo',
                body: 'bar',
                userId: 1
            }
        }).then(function(data) {
            $('#post').append(JSON.stringify(data, null, 4));
        });
    });