require 'nokogiri'
require 'open-uri'

desc "grab info from cbp website"
task :cbp do
  xml = Nokogiri::XML(open('http://apps.cbp.gov/bwt/bwt.xml'))

  garitas = []

  xml.xpath('//port').each do |port|
    text = port.children.first.text
    if text =~ /250301/ || text =~ /250302/
      garitas << port
    end      
  end

  puts garitas
end

