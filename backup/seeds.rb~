# This file should contain all the record creation needed to seed the database with its default values.
# The data can then be loaded with the rake db:seed (or created alongside the db with db:setup).
#
# Examples:
#
#   cities = City.create([{ name: 'Chicago' }, { name: 'Copenhagen' }])
#   Mayor.create(name: 'Emanuel', city: cities.first)

file = Rails.root.to_s + "/db/spreadsheet.csv"
array_from_csv = CSV.read file

Business.destroy_all

i = 0
array_from_csv.each do |row| 
  if i > 0
    score  = row[4] ? row[4] : 2
    Business.create(name: row[0], address1: row[1], address2: row[2] + ', ' +  row[3], score: score, link: row[5])
  end
  i+= 1
end
