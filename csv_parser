require 'csv'

csv_file = 'insert_csv.file here'
csv_text = File.read(csv_file)
csv = CSV.parse(csv_text, :headers => true)

HTML_START = <<-EOS
  <!DOCTYPE html>
  <html>
    <head>
      <meta charset="utf-8">
      <title></title>
    </head>
    <body>
EOS

HTML_END = <<-EOS
    </body>
  </html>
EOS
File.open("sort.html", "w+") do |f|
  f.write HTML_START
  f.write "<h1>Contacts</h1>"
  counter = 1
  csv.each do |row|

    f.write "-------------------------------<br />
      <strong>#{counter}:</strong>
      #{row['first_name']} #{row['last_name']}<br />
      <strong>Client:</strong>    #{row['client']} : #{row['title']}<br />
      <strong>Email:</strong>     #{row['email1']}<br />
      <strong>Phone:</strong>     #{row['phone']}<br /><br />
      <strong>Address:</strong>   #{row['street']} #{row['city']},#{row['state']} #{row['zip']}<br />
      <strong>Comments:</strong>  #{row['comment']}<br /><br /><br />"

      counter += 1
  end

  f.write HTML_END

end
