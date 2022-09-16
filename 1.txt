var request = require("request");
var cheerio = require("cheerio");

request("https://devgo.com.br/", (err, res, body) => {
  if (err) throw new Error(err);

  var $ = cheerio.load(body); // O $ representa o JQuery

  $(".css-1y2n3q5").each(function () {
    var title = $(this).find("a").text();
    console.log(title);
  });
});
